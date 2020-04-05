# Character-Image-Classifier
Classifying images into four classes (Minion, Mickey Mouse, Simson, Poo)

After saving a trained model,

use google cloud platfor - app engine to deploy and launch the app in the browser.

( way to deploy : https://course.fast.ai/deployment_google_app_engine.html )




[ gcloud app deploy에서 생기는 오류 해결 ]
1. app.yaml 파일에 들어가서
" resources:
    memory_gb: 4 " 라인 추가하기
2. dropbox에 파일 업로드 후 링크 생성 (dropbox에 model.pth를 업로드, dropbox를 사용한 것을 추천 )
3. https://www.dropbox.com/s/yw21apbp3yzvwwl/stage-2.pth?dl=0 
   이런 식의 링크 생성 ->  =0을 =1로 바꿔주기
4. server.py 에 model_file_url = 에 3번에서 =1로 바꾼 url 입력
5. model_file_name = 'model'로 내버려두기
6. classes= 자기가 만든 모델 class로 바꿈 (classes = ["Poo","Mickey","Simson","Minion"])
7. 그 이외에 server.py 코드 건들지 말rl
8. cd models 로 디렉토리 이동 -> models.md 파일 이외에 다 삭제
9. "wget (드롭박스 url =1로 바꾼 것)" 명령어를 입력하여 모델 다운로드
10. 다운로드된 모델의 이름이 이상하게 되어있을텐데 model.pth 로 바꿔주기 (cp stage-1.pth?dl=2 model.pth)
11. ~/gitrepo이름/   디렉토리로가서 gcloud app deploy하기
