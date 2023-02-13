# AWS Chime SDK



## Specification

### Meetings and attendees

Client는 secure WebSockets과 Datagram Transport Layer Security (DTLS)을 사용합니다.


### Audio

up to a maximum of 48kHz.

### Video: 

- JavaScript는 1280x720 at 30 frames per second
- iOS, Android, Windows: 1280x720 and 15 frames per second

### Data messages

미팅 참여자끼리 2KB까지 실시간으로 메시지 전송이 가능합니다.

### Content sharing

미리 레코딩된 audio/video 컨텐츠를 비디오는 1280x720 at 15 frames per second, 오디오는 48kHz at 64kbps를 공유 할 수 있습니다.

## Amazon Chime SDK service quotas

![image](https://user-images.githubusercontent.com/52392004/218374065-b3f143c5-4cf0-4b93-acb1-4ba39db4cfbf.png)


[Refeerence]

[Using the Amazon Chime SDK](https://docs.aws.amazon.com/chime-sdk/latest/dg/meetings-sdk.html)

[Amazon Chime SDK를 활용한 영상면접 서비스 개발](https://saramin.github.io/2021-03-09-amazon-chime-sdk-video-interview/)
