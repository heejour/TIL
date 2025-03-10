# 1️⃣ Supabase 로컬 서버 실행 (이미 실행 중이면 생략)

supabase start

# 2️⃣ Edge Function 배포

supabase functions deploy analyze-nutrition

supabase functions deploy generate-feedback

# 3️⃣ 배포된 함수 호출 테스트 (로컬이 아니라 실제 배포된 환경에서 실행됨)

node test-functions.js "{key}"
