# Shape Classifier using TensorFlow.
## TensorFlow.js를 이용한 간단한 도형분류기 웹앱
TensorFlow.js를 이용하여 도형(원,삼각형,사각형)을 분류(inference)하는 웹어플리케이션 예제 소스입니다.
이게 실제 어떻게 돌아가느냐 눈으로 확인하고 싶어서 정말 간단하게 구현한 것이니 참고 부탁드립니다.;-)

## 간단 설명
1. 도형(원,삼각형,사각형) 이미지를 Keras로 학습하여 만든 모델을 TensorFlow.js에서 사용할 수 있게 아래와 같이 모델을 json파일로 저장하는 코드를 한줄 넣어줍니다.(자세한건 https://js.tensorflow.org/tutorials/import-keras.html 여기 참고하세요)
```python
tfjs.converters.save_keras_model(model, tfjs_target_dir)
```
2. 뉴럴넷 모델이 정의된 model.json파일과, weights 정보들이 담긴 파일들이 떨궈집니다.
3. 추론할 수 있는 간단한 웹페이지를 만듭니다.(여기서는 canvas를 이용하여 도형을 그리고, 그 이미지를 tensor로 입력받을 수 있게 적절하게 Array 데이터로 만들어줍니다.(기존 python에서 입력으로 사용한 shape과 동일한 차원)
4. python에서 학습된 모델 불러와서 추론하는 코드와 유사하게 JavaScript 코드로 model.json파일 불러오고 predict하는 함수를 구현하고 추론 결과를 웹페이지에 표시합니다.
5. 무지 간단한 예제이지만 이제 서버사이드에서 추론하지 않고 클라이언트(브라우저)에서 추론할 수 있는 간단한 딥러닝 웹앱이 만들어졌습니다.ㅎ
6. 참고로! 로컬에서 돌려보려면 간단한 웹서버 하나 띄우고 웹브라우저의 CORS(Cross-origin resource sharing)를 허용해야 데모를 확인할 수 있습니다.

![circle](https://raw.githubusercontent.com/choonguri/tfjs_shape_inference/master/images/circle.png)

![rectangle](https://raw.githubusercontent.com/choonguri/tfjs_shape_inference/master/images/rectangle.png)

![triangle](https://raw.githubusercontent.com/choonguri/tfjs_shape_inference/master/images/triangle.png)
