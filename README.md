# Hyperledger-study-45

하이퍼레져 앱 만들기 45실습 일차

출처 : http://dudmy.net/javascript/2015/11/16/javascript-sort/

출처: https://minaminaworld.tistory.com/11 [미나미 블로그]

1. 문자정렬

        var fruit = ['orange', 'apple', 'banana'];

        /* 일반적인 방법 */
        fruit.sort(); // apple, banana, orange

2. 숫자정렬

        var score = [4, 11, 2, 10, 3, 1]; 

        /* 오류 */
        score.sort(); // 1, 10, 11, 2, 3, 4 
                      // ASCII 문자 순서로 정렬되어 숫자의 크기대로 나오지 않음

        /* 정상 동작 */
        score.sort(function(a, b) { // 오름차순
            return a - b;
            // 1, 2, 3, 4, 10, 11
        });

        score.sort(function(a, b) { // 내림차순
            return b - a;
            // 11, 10, 4, 3, 2, 1
        });

3. object 정렬

        var student = [
            { name : "재석", age : 21},
            { name : "광희", age : 25},
            { name : "형돈", age : 13},
            { name : "명수", age : 44}
        ]

        /* 이름순으로 정렬 */
        student.sort(function(a, b) { // 오름차순
            return a.name < b.name ? -1 : a.name > b.name ? 1 : 0;
            // 광희, 명수, 재석, 형돈
        });

        student.sort(function(a, b) { // 내림차순
            return a.name > b.name ? -1 : a.name < b.name ? 1 : 0;
            // 형돈, 재석, 명수, 광희
        });

        /* 나이순으로 정렬 */
        var sortingField = "age";

        student.sort(function(a, b) { // 오름차순
            return a[sortingField] - b[sortingField];
            // 13, 21, 25, 44
        });

        student.sort(function(a, b) { // 내림차순
            return b[sortingField] - a[sortingField];
            // 44, 25, 21, 13
        });

4. 날짜로 정렬

        var data = [
            { '날짜': "2012-11-14", '학년': 3, '점수': 200, },
            { '날짜': "2013-11-14", '학년': 1, '점수': 300, },
            { '날짜': "2017-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2018-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2019-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2020-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2021-11-31", '학년': 3, '점수': 200, },
            { '날짜': "2023-11-01", '학년': 2, '점수': 190, },
            { '날짜': "2002-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2010-11-14", '학년': 2, '점수': 190, },
            { '날짜': "2008-11-14", '학년': 2, '점수': 90, },
            { '날짜': "2009-11-14", '학년': 1, '점수': 100, }
        ];
        console.log(data.sort(date_ascending)); // 오름차순
        function date_ascending(a, b) {
        var dateA = new Date(a['날짜']).getTime();
        var dateB = new Date(b['날짜']).getTime();
        return dateA > dateB ? 1 : -1;
        };

        console.log(data.sort(date_descending)) // 내림차순

        function date_descending(a, b) {
        var dateA = new Date(a['날짜']).getTime();
        var dateB = new Date(b['날짜']).getTime();
        return dateA < dateB ? 1 : -1;
        };
