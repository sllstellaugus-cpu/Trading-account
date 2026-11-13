# MY BINANCE LEDGER v5

웹에서 각자 자신의 바이낸스 API를 이용해 입출금, 선물 손익, 포지션, 체결 기록, 원화 환산 및 1억 원 목표 시뮬레이션을 조회하는 비공식 프로젝트입니다.

## 공개 웹 배포 (최초 1회)

GitHub 저장소 **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root) → Save** 를 선택합니다.

설정 후 GitHub Pages 주소는 보통 `https://sllstellaugus-cpu.github.io/Trading-account/` 형태입니다. 실제 공개 여부는 Pages 설정 화면의 Visit site에서 확인하세요.

## 기술 및 제한

- Cloudflare Worker 403 문제를 피하기 위해 브라우저에서 Binance에 직접 요청합니다. Futures WebSocket API로 현재 선물 잔고·포지션을 우선 조회합니다.
- 입출금·선물 실현손익·체결 기록은 브라우저 직접 REST API입니다. Binance CORS 정책, 지역 제한, 계정 API 권한에 따라 차단될 수 있어 실제 계정 연결 성공이 보장되지 않습니다.
- API Key/Secret Key는 로컬 페이지에서만 사용하며 코드상 서버나 저장소로 전송하지 않습니다. GitHub Pages 호스팅 코드와 브라우저 확장프로그램을 신뢰할 수 있는 환경에서만 사용하세요.
- 이전에 공개되었거나 공유된 키는 반드시 폐기하고, 새 읽기 전용 키만 사용하세요. 거래/출금 권한은 비활성화해야 합니다.
- USDC/USDT 원화 환산은 시세 1달러 가정의 참고치이며 실제 원화 원금과 다를 수 있습니다.
- 손익 기간은 7/30/89일이며, 전체 기간 누적손익이 아닙니다.
- 체결 종목은 손익기록·보유 포지션으로 발견된 종목과 직접 추가한 종목을 조회합니다. 모든 과거 종목이 자동 발견되지는 않습니다.
- 1억 목표일은 선택 기간의 평균 실현손익 또는 사용자가 입력한 하루 순증가액을 이용한 단순 산술 시뮬레이션입니다.

## 검증 현황

JavaScript 문법, 데모 표시, 모의 API 응답 처리 테스트 완료. 실제 바이낸스 개인 계좌 연결은 실계좌 인증 없이 검증되지 않았습니다.
