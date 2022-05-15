팀명 : 투게더<br>
이름 : 김민호 (팀장: 이현준 - 메인제작 및 정리) (팀원 : 이재현 - 기본 페이지 제작)<br>
졸업작품 사이트 URL : <br>
포트폴리오 소개 사이트 URL :<br>

# [졸업 작품 소개]
- 작품명 : 이두박근
- 개발환경 : 안드로이드 스튜디오
- 작품 소개 : 어플을 사용해서 내가 오늘 무슨 운동을 얼마나 했는지 기록할 수 있고 내가 원하는 부위에 운동들을 검색해서 내가 필요한 운동의 방법이나 도움을 얻을 수 있게 도움을 줄 수 있는 어플을 구성하려한다.
- 작품의 특징 : 내가 요일마다 어떤 운동을 했는지 기록해 놓음에 따라서 이번주 오늘 다음날 내가 어떤부위 어떤운동을 해야할지 알기 쉽게 도움을 받을 수 있다.

# [개발일지]

@ 5월 11일

오늘은 운동소개 방법 페이지에 들어갈 다양한 운동들의 종류 방법 주의사항 들을 조사해서 하체와 상체 자료들을 수집하였다(밑에는 그중에서 두가지를 예로 가져와 보았습니다 )

※ 렛플 다운
@ 렛 = 바
@ 플 다운 = 내린다 로 바를 내리는 운동이라고 생각하시면 됩니다.
- 바를 목적에 맞게 연결해준다
- 먼저 허벅지를 빈공간 없이 밀착시킨다
- 바를 어깨넓이보다 살짝 넓게 잡고 바를 쇄골 윗가슴높이까지 당겨준다
- 올라갈때는 허리가 너무 휘지않고 천천히 팔을 뻗어준다
 
X 주의사항 : 먼저 앉은자세에서 허벅지에 빈공간이 생기지 않도록 의자 높이를 조절
내가 자극을 받고 싶은 부위를 생각하면 바를 선택한다
바를 당기고 올라갈때에는 팔꿈치를 다 펴서는 안된다
 
※ 벤치 프레스
 
- 벤치에 누운상태에서 어깨와 엉덩이를 벤치에 붙인 상태에서 허리는 살짝 띄어서 아치형을 만들어 준다
- 턱을 가슴쪽으로 당긴다음 바벨은 어깨넓이보다 살짝 넓게잡아준다
- 바벨을 들어올려 시작위치는 가슴의 정중앙으로 끌어온다음 당겨주고 밀어준다
 
X 주의사항 : 먼저 운동시에 몸이 움직이지 않도록 다리를 고정하고 허리에 공간을 조금 만들어주고
바벨을 내릴 때 팔꿈치가 너무 바깥쪽으로 벌어지지 않도록 해야하고
팔을 펼때는 너무 반동의 힘을 이용해 튕기지 않도록 한다


@ 5월 4일
오늘은 우리조의 주제에 있어서 운동방법을 소개하고 그 운동들을 나열할 수 있는 리스트 목록 페이지를 만들었습니다 저번주에 사용할 listview를 사용하려고 했지만 그렇게하면 데이터 양이 너무 방대하게 커질것같아서 버튼으로 리스트 목록을 수정하였습니다
~~~javascript
<Button
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:text="상체운동 리스트"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:layout_gravity="center"
        android:backgroundTint="#573535"
        android:textSize="30dp"
        android:layout_marginTop="-10dp"
        android:layout_marginBottom="10dp"
        />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">


        <Button
            android:layout_width="match_parent"
            android:layout_height="80dp"
            android:backgroundTint="#AEDEE4"
            android:textSize="20dp"
            android:textColor="#0F8DF1"
            android:text="벤치 프레스" />
~~~

@ 4월 27일 <br>
오늘은 listview를 사용해서 어플에서 운동방법을 볼수있는 초기화면 을 구성하였고 부족한 소개페이지에 html을 사진을 추가해보았습니다

- html 홈페이지 꾸미기

~~~javascript
<section class="sec-cont row2">
      <div class="cont-card3">
        <div class="card1 card">
          
          <!-- <div class="cont-text">
            <h1>HTML</h1>
            <p>the language for building web pages</p>
          </div> -->
          <a href="#" class="btnn">BMI 지수 체크하기</a>
        </div>
        <div class="card2 card">
          <a href="#" class="btnn">메인 페이지</a>
        </div>
        <div class="card3 card">
          <a href="#" class="btnn">운동법 알아보기</a>
        </div>
      </div>
    </section>
 ~~~
 - listview를 사용해서 리스트 목록 작성하기 (adapter 사용구문)
~~~javascript

final TextView tvSelect = findViewById(R.id.tv_select);
        ListView listView = findViewById(R.id.listView);

        List<String> list = new ArrayList<>();
        list.add("1번운동");
        list.add("2번운동");
        list.add("3번운동");
        list.add("4번운동");

ArrayAdapter<String>adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, list);
        listView.setAdapter(adapter);

        listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> adapterView, View view, int position, long l) {
                String data = (String) adapterView.getItemAtPosition(position);
                tvSelect.setText(data);
~~~

@ 4월 13일 <br>

오늘은 작품 소개 페이지 제작을 해보았다 저번학기까지 배운 html 코드를 이용해서 간단한 페이지 제작을 실행하고 있다. 오늘 만든 구성요소중 jd슬라이드를 이용하여 만든 슬라이드 html코드 및 css코드이다

- 슬라이드 배너 html 코드
~~~javascript
<section class="jd-slider main-slider main-visual">
      <div class="slide-inner">
          <ul class="slide-area">
              <li>
                  <a href="#"><img src="Img/g1.jpeg" alt="image01">
                    <dl>
                      <dt class="tit">이두박근 피트니스</dt>
                      <!-- <dd>**</dd> -->
                    </dl>
                  </a>
              </li>
              </ul>
        </div>
  </section>
~~~
- jd슬라이더를 이용하려면 이 스크립트 코드가 필수적으로 들어가야 한다.
~~~javascript

<script>
        window.onload = function () {
          
          $('.main-slider').jdSlider({
                wrap: '.slide-inner',
                isAuto: true,
                isLoop: true
            });
            $('.slider').jdSlider({
                wrap: '.slide-inner',
                slideShow: 4,
                slideToScroll: 1,
                isLoop: true,
                responsive: [{
                    viewSize: 768,
                    settings: {
                        slideShow: 1
                    }
                }]
            });
            
        };
    </script>


~~~

@ 4월 6일 <br>
초기 구상안중 5번째 페이지로 동영상이나 이미지로 시각자료를 보여주면서 textview 와 imageview 를 이용해서 운동방법을 알아볼 수 있는 창과 그 운동을 할때 주의사항 칸을 만들었고 그안에 들어갈 내용들을 조사해 보았다 
~~~javascript
<ImageView
            android:id="@+id/exerciseImage"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:layout_margin="10dp"
            android:src="@drawable/img1" />

<TextView
            android:id="@+id/explanation"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:layout_marginTop="100dp"
            android:text="운동방법"
            android:textSize="25dp" />
~~~
            


@ 3월 30일 <br>
초기 구성안중 두번째 페이지인 운동방법 설명창 및 오늘 자신이 한 운동을 작성할수 있는 선택창과 선택 버튼을 구성하여 페이지를 제작하였다운동 설명창 답게 상단에 사진을 넣어서 시각효과를 더 극대화 할 수 있도록 하였고 밑에는 일지작성 버튼 및 내가 필요한 운동들을 더 찾아볼 수 있는 버튼들도 구성해 두었다.

@ 3월 23일 <br>
처음에는 가장 많이 배운 페이지 제작을 하려 했지만 이번 학기에 배우는 안드로이드 스튜디오과목에서 흥미를 느껴서 안드 스튜디오를 사용해 공부하면서 만들어 보면 좋을 것 같아서 안드 스튜디오를 사용하여 요즘 시즌이 봄시즌이기도 하고 여름을 앞 두고 있으니 운동에 관심을 가지는 사람들이 늘어나고 있어서 운동 관련 일지 어플로 주제를 선정하고 초기 구성화면을 토의해 보았다.


