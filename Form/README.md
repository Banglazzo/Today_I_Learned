# 2020-10-29 form1
오늘은 따로 내용을 정리하지 않고 html파일 하나를 작성했습니다.


기본적인 폼만드는 것을 연습한 파일입니다.


더 심화된 폼은 다음번에..


(밑에는 보기 쉬우라고 코드블럭을 추가해봤어요.)
``` html
    <!DOCTYPE html>
<html lang = "ko">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-compatible" content="ie=edge">
        <title>Form Making</title>
    </head>

    <body>
        <h1>기본 폼(서술형 폼)</h1>
        <form action="search.php" method="post" autocomplete="off">
            <input type="text" title="검색">
            <input type="submit" value="검색">
            <h1>선택형 폼</h1>
            <h3> 선택 과목(1과목만 선택 가능)</h3>
            <ul>
                <li>
                    <label><input type="radio" name = "subject" value="Physics.1">물리1</label>
                </li>
                <li>
                    <label><input type="radio" name="subject" value="Chemistry.1">화학1</label>
                </li>
                <li>
                    <label><input type="radio" name="subject" value="Life Science.1">생명과학1</label>
                </li>
                <li>
                    <label><input type="radio" name="subject" value="Earth science.1">지구과학1</label>
                </li>
            </ul>
            <h1>회원가입폼 만들기(폼 요소 그룹으로 묶기)</h1>
            <fieldset>
                <legend>기본 정보 입력</legend>
                <h4>*은 필수로 입력해야함.</h4>
                <ul>
                    <li>
                        <label for="name">*이름(10자이내)</label>
                        <input type="text" maxlength="10" id="name">
                    </li>
                    <li>
                        <label for="date">생년월일</label>
                        <input type="date" id="date">
                    </li>
                    <li>
                        <label for="number">*전화번호</label>
                        <input type="tel" id="number">
                    </li>
                </ul>
            </fieldset>
            <fieldset>
                <legend>가입 정보 입력</legend>
                <ul>
                    <li>
                        <label for="email">*아이디(이메일)</label>
                        <input type="email" id="email">
                    </li>
                    <li>
                        <label for="Password">*비밀번호</label>
                        <input type="password" id="Password">
                    </li>
                    <li>
                        <label for="Password">*비밀번호 재입력</label>
                        <input type="password" id="Password">
                    </li>
                </ul>
            </fieldset>
        </form>
    </body>
</html>
```
# 2020-12-01 form2
정신 없이 사는 바람에 이제서야 들고왔습니다. 


저번 폼과 크게 다를 건 없지만


저번 폼에 들어가지 않았던 요소들을 조금 더 추가해보았습니다.


오늘도 역시 코드블럭과 html 문서 하나 남깁니다.


``` html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-compatible" content="ie=edge">
    <title>form making2</title>
</head>
<body>
    <h1>회원 가입 폼</h1>
    <form>
        <fieldset>
            <legend> 기본 정보 </legend>
            <ul>
                <li>
                    <label> *아이디:<input type="text" autofocus placeholder="15자 이내로 입력" id="user_id" size="15" required></label>
                    <input type="button" value="중복 확인" onclick="window.open()">
                    <input type="hidden" name="user_id" value="Y">
                </li>
                <li>
                    <label> *비밀번호: <input type="password" id="user_password" autofocus required></label>
                </li>
                <li>
                    <label> 이메일: <input type="email" id="user_email" autofocus></label>
                    <input type="hidden" name="user_email" value="y">
                </li>
                <li>
                    <label> 전화번호: <input type="tel" id="user_number" autofocus></label>
                    <input type="submit" value="가입하기">
                </li>
            </ul>
        </fieldset>
        <h1>주문 제작 티셔츠 주문 폼</h1>
        <fieldset>
            <legend>주문 정보</legend>
            <ul>
                <li>
                    <label>티셔츠 종류(원하시는 항목을 고르시면 제품 번호가 자동으로 입력됩니다.)</label>
                    <input type="text" id="choice" list="T-shirt">
                    <datalist id="T-shirt">
                        <option value="847328">반팔 오버핏 티셔츠</option>
                        <option value="847329">반팔 슬림핏 티셔츠</option>
                        <option value="847330">7부 오버핏 티셔츠</option>
                        <option value="847331">7부 슬림핏 티셔츠</option>
                        <option value="847332">긴팔 오버핏 티셔츠</option>
                        <option value="847333">긴팔 슬림핏 티셔츠</option>
                    </datalist>
                </li>
            
                <li>
                    <label>티셔츠 색상</label>
                    <input type="color" value="#ffffff">
                </li>
                <li>
                    <label> 티셔츠에 들어갈 사진 <input type="file"> </label>
                </li>
                <li>
                    <label> 주문 수량(최소 10장) <input type="number" min="10" max="500" value="10"></label>
                </li>
            </ul>

        </fieldset>

        <input type="button" value="주문하기">
    </form>
</body>
</html>
```