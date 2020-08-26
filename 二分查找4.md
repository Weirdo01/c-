/** 
 * Forward declaration of guess API.
 * @param  num   your guess
 * @return 	     -1 if num is lower than the guess number
 *			      1 if num is higher than the guess number
 *               otherwise return 0
 * int guess(int num);
 */

int guessNumber(int n){
    unsigned int pick = n/2;
    char ret = 0;
    unsigned int min = 0;
    unsigned int max = n;

    ret=guess(pick);
	while(ret !=0 ){

        if(ret==-1){
            if(pick - min == 1) return min;
            max = pick;
            pick-=(pick-min)/2;
        }else{
            if(max - pick == 1) return max;
            min = pick;
            pick+=(max-pick)/2;
        }

        ret=guess(pick);
    }
    return pick;
}
