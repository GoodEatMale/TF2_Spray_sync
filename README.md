# TF2_Spray_sync
Bring custom sprays back to TF2 Casual! This lightweight, automated client syncs .vtf files in the background. See each other's custom sprays on official Casual servers again! Zero FPS drop.

> **💡 AI Assistance Acknowledgment**
> 본 프로그램의 코드 개발 및 이 문서의 영문 번역은 **구글 제미나이(Google Gemini)**의 도움을 받아 진행되었습니다.
> This program was developed, and this README was translated into English, with the assistance of **Google Gemini**.

---

## 🇰🇷 한국어 설명 (Korean)

이 파일은 제 서버와 연결해 사람들과 스프레이를 공유하는 프로그램입니다.
해당 프로그램은 커뮤니티 서버가 활성화 되어있지 않은 아시아권 유저들을 타겟으로 만들어졌으며 캐주얼 매치에서도 스프레이를 볼 수 있도록 합니다.

**사용법**
파이썬 파일을 그대로 받아서 실행 시키셔도 되고, 아니면 제 유튜브를 참고해서 받아가셔도 좋습니다.
* [유튜브 사용 설명 영상 보러가기](https://youtu.be/TtRg5_EFkFI?si=BkktGHE3S_FJGreE)

**원리**
원리는 간단합니다. 스프레이를 사용할 때에는 해시값을 가진 스프레이 파일이 `\temp` 폴더에 쌓입니다. 이걸 서버에 연결해서 서버 이용자들한테 뿌리면 이용자들끼리 스프레이를 볼 수 있지만 캐주얼 매치에서는 업로드 및 다운로드를 막아 스프레이를 뿌려도 `\temp` 폴더에 해시값의 파일만 생성될 뿐 업로드 되질 않습니다.
이 원리를 이용해 제가 가진 서버를 이용하여 프로그램 사용자의 `\temp` 파일을 업로드 및 다운로드 시켜 프로그램 사용자들끼리 보일 수 있게 만들었습니다.
물론 `\temp` 폴더는 캐시를 저장하는 역할이기 때문에 게임을 종료할 시 파일이 삭제되지만, 프로그램은 `%appdata%`에 백업(`TFSpray_Vault`) 폴더를 만들어 컴퓨터 내에서 복구할 수 있도록 하여 통신 데이터 사용량을 줄였습니다.

**보안 및 안전성**
보안 또한 등한시 하지 않았습니다.
* 먼저 512KB 이상, 확장자 명이 `.vtf` 파일이 아닌 것, 해시값의 형태를 가지지 않은 파일, 앞의 특정 문자가 오지않는 파일의 경우 업로드와 다운로드를 막아두었습니다.
* 개인정보에 대해서도 업로드 되는 파일은 `\temp` 폴더 파일 뿐 다른 파일은 일체 볼 수 없으며 다운로드 당사자의 IP, MAC 그 어떤 정보도 볼 수 없습니다.
* **VAC 밴 위험 없음:** 이 프로그램은 파일 및 메모리의 변조 기능은 일체 들어가있지 않고 단순히 캐시 폴더에 파일을 집어넣는 용도로만 만들어져있기 때문에 밴을 당할 가능성은 없습니다.

이상 설명을 마치며 즐거운 캐주얼 매치 되시길 바랍니다.
여러분의 스프레이를 캐주얼 매치에서 보길 빌며 박미르 올림.

**Q&A 및 건의사항**
추가 질문 사항이나 건의는 아래 디스코드에서 환영합니다!
* [디스코드 서버 참여하기](https://discord.gg/tsuMWykyCE)

---

## 🌐 English Description

This program connects to a dedicated server to share TF2 sprays among users. 
It is primarily designed for players in the Asian region where community servers are less active, enabling everyone to see sprays even in Official Casual Matches.

**🚀 How to Use**
You can either download and run the Python script directly, or refer to my YouTube video for installation instructions and the executable file.
* [Watch the Video Guide](https://youtu.be/TtRg5_EFkFI?si=BkktGHE3S_FJGreE)

**⚙️ How It Works**
The mechanism is simple. When you use a spray in-game, a spray file with a specific hash value is generated in your `\temp` folder. Normally, community servers distribute these files so players can see each other's sprays. However, Valve's official Casual Matches block this upload/download process, meaning your spray only creates a local file on your computer and is never shared.

This program bypasses that restriction. It uses my external server to sync (upload & download) these `\temp` files among the program users, making sprays visible to everyone running the client in Casual Matches.

Furthermore, since the `\temp` folder acts as a cache, TF2 automatically deletes its contents when the game closes. To prevent re-downloading everything and to reduce network data usage, this program creates a local backup vault (`%appdata%\TFSpray_Vault`) to instantly restore your spray cache locally.

**🛡️ Security Measures**
We did not overlook security. 
* **Strict File Filtering:** The server strictly blocks the upload and download of any files that are over 512KB, do not have a `.vtf` extension, or do not match the specific hexadecimal hash filename structure required by TF2.
* **Privacy Guaranteed:** The client strictly accesses ONLY the `\temp` folder. No other files on your computer are touched. Additionally, no personal information (such as the downloader's IP or MAC address) is collected or viewable.
* **100% VAC Safe:** There is zero risk of getting a VAC ban. This program does not inject into the game memory or modify any core game files. It simply reads and writes standard texture files in the designated cache folder.

Have a great time in Casual Matches! 
I look forward to seeing your amazing sprays on the battlefield.

— *Mireu Park*

**💬 Q&A and Feedback**
All feedback and inquiries are welcome in our Discord!
* [Join the Discord Server](https://discord.gg/tsuMWykyCE)
