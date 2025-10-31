# Instagram Insights 수집기 - 사용 가이드

Instagram Business/Creator 계정의 인사이트 데이터를 자동으로 수집하여 서버 API로 전송하는 Windows 애플리케이션입니다.

## 다운로드 및 설치

### 설치 파일

최신 설치 버전: [InstagramInsights_setup.exe](https://github.com/picory/instagram-insights-release/releases/download/1.0.1/InstagramInsights_setup.exe)

1. 위 링크에서 설치 파일을 다운로드합니다.
2. 다운로드한 `InstagramInsights_setup.exe` 파일을 실행합니다.
3. 설치 마법사를 따라 설치를 완료합니다.

## 시리얼 키 인증

앱을 처음 실행하면 시리얼 키 입력 창이 나타납니다.

- 시리얼 키가 필요한 경우 문의하세요. (카카오톡 문의: bitsense)
- 시리얼 키 형식: `XXXX-XXXX-XXXX-XXXX`

## API 설정

### 설정 항목

앱 실행 후 **"API 설정"** 버튼을 클릭하여 다음 정보를 입력합니다:

#### 1. Instagram API (옵선)

```
IG User ID: ...
IG Access Token: ...
```

#### 2. Facebook App(옵션)

```
FB App ID: ...
FB App Secret: ...
```

#### 3. Instagram App (옵션)

```
IG App ID: ...
IG Secret Code: ...
```

#### 4. WordPress API (데이터 수집 서버)

```
WP API Base URL: https://labs.picory.com/wp-json/instagram-insights/v1/
WP API Key: (문의 필요)
```

### 설정 방법

1. 앱 메인 화면에서 **"API 설정"** 버튼 클릭
2. 각 항목에 제공받은 정보 입력
3. **"저장"** 버튼 클릭
4. 설정이 완료되면 자동으로 `%USERPROFILE%\.instagram_insights\.env` 파일에 저장됩니다.

## 사용법

### 기본 사용

1. **계정 확인**

   - "계정 목록 확인" 버튼을 클릭하여 등록된 Instagram 계정을 확인합니다.
   - 활성/비활성 상태를 확인할 수 있습니다.

2. **데이터 수집 시작**

   - "수집 시작" 버튼을 클릭합니다.
   - 오른쪽 로그 영역에서 진행 상황을 확인할 수 있습니다.

3. **수집 중단**
   - 진행 중인 수집을 중단하려면 "수집 정지" 버튼을 클릭합니다.

### 자동화 설정

#### 1. OS 시작 시 자동 실행

- "OS 시작시 자동으로 실행" 체크박스를 선택합니다.
- Windows 시작 프로그램에 등록되어 부팅 시 자동으로 앱이 실행됩니다.

#### 2. 앱 시작 시 자동 수집

- "앱 시작시 자동으로 수집 시작" 체크박스를 선택합니다.
- 앱이 실행되면 즉시 데이터 수집을 시작합니다.

#### 3. 스케줄 설정

- "수집 시작 시간"에서 원하는 시간을 설정합니다 (예: 09:00).
- 매일 해당 시간에 자동으로 데이터 수집이 실행됩니다.

## 데이터 수집 API

### 기본 API 엔드포인트

```
https://labs.picory.com/wp-json/instagram-insights/v1/
```

### API 기능

- **계정 인사이트 수집**: 계정 전체 통계 데이터 (도달, 참여, 상호작용)
- **미디어 수집**: 게시물 및 릴스 정보 (캡션, 좋아요, 댓글 수 등)
- **미디어 인사이트**: 개별 미디어의 도달, 조회수, 저장 등

### 커스텀 API

WordPress 플러그인을 통해 커스텀 가능합니다.

- API KEY 발급이 필요합니다 (문의 필요).

## 설정 파일 위치

모든 설정은 다음 경로에 저장됩니다:

```
%USERPROFILE%\.instagram_insights\
├── .env              # API 설정 (자동 생성)
└── gui_config.json   # GUI 설정 (자동 생성)
```

## 주의사항

1. **Instagram 계정 요구사항**

   - Instagram Business 계정 또는 Creator 계정이 필요합니다.
   - 개인 계정에서는 Insights API를 사용할 수 없습니다.
   - Facebook 페이지와 Instagram 계정이 연결되어 있어야 합니다.

2. **API 키 보안**

   - API KEY는 외부에 노출되지 않도록 주의하세요.
   - 설정 파일은 사용자 홈 디렉토리에 안전하게 저장됩니다.

3. **네트워크 연결**
   - 데이터 수집 중에는 안정적인 인터넷 연결이 필요합니다.

## 문의

- 시리얼 키 발급: 문의 필요
- 수집 API KEY: 문의 필요
- 기술 지원: GitHub Issues

## 최신 버전 확인

앱은 자동으로 업데이트를 확인합니다:

- 새 버전이 있으면 화면 하단에 알림이 표시됩니다.
- 알림을 클릭하여 즉시 업데이트할 수 있습니다.

최신 버전 다운로드: [GitHub Releases](https://github.com/picory/instagram-insights-release/releases)
