class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int l = 1, r = s.size(), ans = 0, cntCharacters[256];
        while(l <= r) {
            int mid = (l + r) / 2;
            
            for (int i = 0; i < 256; i++) {
                cntCharacters[i] = 0;
            }

            int cntOnes = 0;
            for (int i = 0; i < mid; i++) {
                int c = int(s[i]);
                if (cntCharacters[c] == 0) {
                    cntOnes++;
                } else 
                if (cntCharacters[c] == 1) {
                    cntOnes--;
                }
                cntCharacters[c]++;               
            }

            int answer = cntOnes == mid;
            for (int cur = mid; cur < s.size(); cur++) {
                int last = cur - mid;
                int cLast = int(s[last]);
                int cCur = int(s[cur]);
                if (cntCharacters[cLast] == 1) {
                    cntOnes--;
                } else 
                if (cntCharacters[cLast] == 2) {
                    cntOnes++;
                }
                cntCharacters[cLast]--;   

                if (cntCharacters[cCur] == 0) {
                    cntOnes++;
                } else 
                if (cntCharacters[cCur] == 1) {
                    cntOnes--;
                }
                cntCharacters[cCur]++;   
                answer += cntOnes == mid;
            }

            if (answer > 0) {
                ans = mid;
                l = mid + 1;
            } else {
                r = mid - 1;
            }
        }
        return ans;
    }
};
