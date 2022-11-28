# Java_Programmers 문제풀이

### 피자 나눠먹기(2)
* LV 0
```
int solution(int n) {
    int answer = 0;
    for(int i = 1;i>0;i++){
        if((6*i)%n==0)return i;
    }
    return answer;
}
```

### 피자 나눠먹기(3)
```
int solution(int slice, int n) {
    int answer = 0;
    if(n%slice == 0){
        return (n/slice);
    }else{
        return (n/slice)+1;
    }
    
    return answer;
}
```

### 옷가게 할인받기
```
int solution(int price) {
    int answer = 0;
    if(price>=100000 && price<300000){
        return price*0.95;
    }else if(price >= 300000 && price <500000){
        return price*0.9;
    }else if(price>=500000){
        return price * 0.8;
    }else{
        return price;
    }
    
    return answer;
}
```
### 아이스 아메리카노
```
class Solution {
    public int[] solution(int money) {
        int a1 = money/5500;
        int a2 = money%5500;
        int[] answer = {a1,a2};
        return answer;
    }
}
```

### 배열 뒤집기

```
class Solution {
    public int[] solution(int[] num_list) {
        int[] answer = new int[num_list.length];
        for(int i = 0;i<num_list.length;i++){
            answer[i] = num_list[num_list.length-1-i];
        }
        return answer;
    }
}
```

### 문자열 뒤집기
```
class Solution {
    public String solution(String my_string) {
        String answer = "";
        String temp = "";
        for(int i = 0;i<my_string.length();i++){
            String tp = my_string.substring(my_string.length()-1-i,my_string.length()-i);
            temp = temp + tp;
        }
        answer = temp;
        return answer;
    }
}
```
### 직각삼각형 출력하기
```
public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        String temp = "";
        for(int i=1;i<=n;i++){
            temp = temp + "*";
            System.out.println(temp);
        }

    }
}
```
### 짝수 홀수 개수

```
class Solution {
    public int[] solution(int[] num_list) {
        int a = 0; int b = 0;
        int[] answer = {a,b};
        for(int i = 0;i<num_list.length;i++){
            if(num_list[i]%2 ==0)a++;
            else{b++;}
            
        }
        answer[0]=a;answer[1]=b;
        return answer;
    }
}
```
### 문자 반복 출력하기
```
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        for(int i = 0;i<my_string.length();i++) {
        	answer = answer + my_string.substring(i,i+1).repeat(n);
        }
        return answer;
    }
}
```
### 특정 문자 제거하기
* 문자열은 ==으로 비교하면, 값이 같아도 다르게 뜰 수 있음.
* equals로 비교해야함.
```
class Solution {
    public String solution(String my_string, String letter) {
        String answer = "";
        for(int i = 0;i<my_string.length();i++){
            if(my_string.substring(i,i+1).equals(letter)==false){
                answer = answer + my_string.substring(i,i+1);
            }else{
                answer = answer;
            }
        }
        return answer;
    }
}
```
### 배열자르기
```
class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = new int[num2-num1+1];
        int j = 0;
        for(int i = num1;i<=num2;i++){
            answer[j]=numbers[i];
            j++;
        }
        return answer;
    }
}
```
### 외계행성의 나이

```
class Solution {
    public String solution(int age) {
        String answer = "";
        String[] alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".toLowerCase().split("");
        int i = 0;
        int j = 1000;
        if(age/1000!=0){
        	while(i<4) {
        		answer = answer + alphabet[age/j];
        		age = age - j*(age/j);
        		i++;
        		j = j/10;
        	}
        }else if(age/100!=0){
        	j = 100;
            while(i<3) {
        		answer = answer + alphabet[age/j];
        		age = age - j*(age/j);
        		i++;
        		j = j/10;
            }
        }else if(age/10!=0){
        	j = 10;
            while(i<2) {
        		answer = answer + alphabet[age/j];
        		age = age - j*(age/j);
        		i++;
        		j = j/10;
            }
        }else{
            j = 1;
    		answer = answer + alphabet[age/j];
        }
        return answer;
    }
}
```

### 최빈값 구하기
```
class Solution {
    public int solution(int[] array) {
        int answer = 0;
        
        int [] index = new int[1000];
        
        for(int i = 0;i<array.length;i++) {
        	index[array[i]]++;
        }
        int max = 0;
        for(int i = 0; i<index.length;i++){
        	if(max<index[i]) {
        		max=index[i];
        	}
        }
        int str = 0; int cnt = 0;
        for(int i = 0;i<index.length;i++) {
        	if(index[i]==max) {
        		str = i;cnt++;
        	}
        }
        if(cnt==1) {
        	answer = str;
        }else {
        	answer = -1;
        }
        
        return answer;
    }
}
```
### 짝수는 싫어요
```
class Solution {
    public int[] solution(int n) {
        int[] answer = new int[(n/2)+(n%2)];
        int idx=0;
        for(int i = 1;i<=n;i++) {
        	if(i%2==1) {
        		answer[idx] = i;idx++;
        	}else {
        		continue;
        	}
        }
        return answer;
    }
}
```
### 피자 나눠먹기
```
class Solution {
    public int solution(int n) {
        int answer = 0;
        if(n==0) {
        	answer = 0;
        }else if(n%7!=0){
        	answer = n/7+1;
        }else {
        	answer = n/7;
        }
        return answer;
    }
}
```
### 진료 순서 정하기
```
        int[] answer = new int[emergency.length];
        
        int j = 1; int idx = 0;int max = 0;
        
        while(j<emergency.length+1) {
        for(int i = 0;i<emergency.length;i++) {
        	if(emergency[i]>max) {
        		max = emergency[i];idx = i;
        		}
        	}
        	answer[idx] = j;j++;max = 0;emergency[idx]=0;idx=0;
        }
        return answer;
    }
}
```
### 순서쌍의 개수
```
class Solution {
    public int solution(int n) {
    	int cnt = 0;
    	for(int i = 1;i<=n;i++) {
    		if(n%i==0) cnt++;
    	}
        int answer = cnt;
        return answer;
    }
}
```
### 개미 군단
```
class Solution {
    public int solution(int hp) {
    	int n1,n2,n3;
    	n1 = hp/5; hp = hp-n1*5;
    	n2 = hp/3;hp=hp-n2*3;
    	n3 = hp;
        int answer = n1+n2+n3;
        return answer;
    }
}
```

### 구슬을 나누는 경우의수
```
class Solution {
	static double fac(double a) {
		double as = 1;
		if(a==0)return 1;
		while(a>0) {
			as = as*a;
			a--;
		}return as;
	}
    public static double solution(double balls,double share) {
    	double answer = 0; double n; double m;
    	if(share ==0 || balls == share) return 1;
    	
    	// 그대로
    	if(share<balls/2) {
    	 n = balls;m = share;
    	// else : share : balls-share
    	}else {
    	n = balls;m = balls-share;
    	}
    	
    	answer = Math.round((fac(balls)/(fac(balls-share)*fac(share))));
        return answer;
    }
}
```