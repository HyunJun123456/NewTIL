<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>연습1</title>
    <style>
        body{
            width:1024px;
        }
       
       
        .logo{
            float: left;
        }
        .login{
            float:right;
        }
        .menu{
            clear:both;
        }
        .menu>ul{
            list-style: none;
        }
        .menu>ul>li{
            display:inline-block;
            margin-right:10%;
        }
        #header>h1{
            float:left;
            margin-left:20%;
            
        }
        #footer{
            text-align: center;
            background-color: aquamarine;
            height:80px;
            width:100%;
            padding-top:3%;
        }
        #container{
            background-color: gray;
            height: 400px;
            width:100%;
        }
    </style>
</head>
<body>
    <div id="header">
        <div class="logo">
            <img src="https://cdn.nbntv.co.kr/news/photo/202112/944008_53117_1134.png" width=200px">
        </div>
        
        <h1>MYMain</h1>
        
        <div class="login">
            <form>
                <table>
                    <tr>
                        <td>아이디</td>
                        <td><input type="text" name="id"></td>
                    </tr>
                    <tr>
                        <td>패스워드</td>
                        <td><input type="password" name="pw"></td>
                    </tr>
                    <tr>
                        <td colspan="2">
                            <input type="submit" value="로그인">
                            <input type="reset" value="취소">
                        </td>
                    </tr>
                </table>
            </form>
        </div>

        <div class="menu">
            <ul>
                <li>메인</li>
                <li>공지사항</li>
                <li>자유게시판</li>
                <li>갤러리</li>
                <li>회원관리</li>
                <li>채팅하기</li>
            </ul>
        </div>    

    </div>

    <div id="container">
        <p>content내용</p>
    </div>
    
    
        <div id="footer">
            <p>Copyright c 1998-2019 multi information Educational Institute All Right Reserved</p>
        </div>
    
</body>
</html>

테스트 파일