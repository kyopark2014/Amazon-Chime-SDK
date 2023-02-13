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



## realtimeSendDataMessage

realtimeSendDataMessage(topic: String, data: Any, lifetimeMs: Int): Unit

Data message는 audio/video가 시작된 후에 데이터 채널을 이용하여 topic과 함께 전송할 수 있습니다. 서버쪽에서 최대 5분간 LifetimeMs로 저장됩니다.  

- topic - : String - topic the message is sent to

- data - : Any - data payload, it can be ByteArray, String or other serializable object, which will be convert to ByteArray

- lifetimeMs - : Int - the milliseconds of lifetime that is available to late subscribers, default as 0



## Pricing

### Connection to Amazon Chime SDK WebRTC media session: $0.0017 (Rate Per minute (each attendee)
 연결 되면 과금됨 (screen share, screen view, two-way audio, one-way audio, two-way video, or one-way video)
100명이 60분동안 미팅: 100 x 60 x 0.0017 = $10.2

### Live connector to send video to third-party streaming platform
1 HD video stream x 60 minutes x $0.09 per stream-minute = $5.4 per session


### Messaging
Messaging is pay-per-use with rates for sending messages, message delivery, and message storage. The Amazon Chime SDK only charges you for what you use, allowing you to scale as needed. 

![image](https://user-images.githubusercontent.com/52392004/218378732-e7162d78-6d0b-4da5-b046-f1f3f4b020e5.png)


- 1MB를 2KB 단위로 잘라서 보내는 경우: 512번 전송이 되어야 함
- 100명과 대화중 1MB파일 1개 전송: 512 x 100 x 0.0007 = $35.84



[Refeerence]

[Using the Amazon Chime SDK](https://docs.aws.amazon.com/chime-sdk/latest/dg/meetings-sdk.html)

[Amazon Chime SDK를 활용한 영상면접 서비스 개발](https://saramin.github.io/2021-03-09-amazon-chime-sdk-video-interview/)

[realtimeSendDataMessage](https://aws.github.io/amazon-chime-sdk-android/amazon-chime-sdk/com.amazonaws.services.chime.sdk.meetings.realtime/-default-realtime-controller/realtime-send-data-message.html)

[Amazon Chime SDK Whiteboard with Data Messages for Real-time Signaling](https://dannadori.medium.com/amazon-chime-sdk-whiteboard-with-data-messages-for-real-time-signaling-c0740575a6c0)

