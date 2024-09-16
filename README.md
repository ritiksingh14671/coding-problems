class Solution {
    public boolean isHappy(int n) {
        int slow = n;
        int fast = n;

        do{
            slow = square(slow);
            fast = square(square(fast));
        }while(slow != fast);

        if(slow == 1 || fast == 1){
            return true;
        }
        return false;
    }
    private int square(int number){
        int ans = 0;
        while(number > 0){
            ans += (number % 10) * (number % 10);
            number /= 10;
        }
        return ans;
    }
}
