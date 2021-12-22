```java
class Solution {
    public int strStr(String haystack, String needle) {
        if (needle.length() == 0) return 0;
        int[] next = new int[needle.length()];
        getNext(next, needle);
        int j = 0; 
        for (int i = 0; i < haystack.length(); i++) {
            while (j > 0 && haystack.charAt(i) != needle.charAt(j)) {
                j = next[j - 1];
            }
            if (haystack.charAt(i) == needle.charAt(j)) {
                j++;
            }
            if (j == needle.length()) {
                return i - needle.length() + 1;
            }
        }
        return -1;
    }

    public void getNext(int[] next, String needle) {
        next[0] = 0;
        int prefixEnd = 0;
        for (int suffixEnd = 1; suffixEnd < needle.length(); suffixEnd++) {
            while (prefixEnd > 0 & needle.charAt(prefixEnd) != needle.charAt(suffixEnd)) {
                prefixEnd = next[prefixEnd - 1];
            }
            if (needle.charAt(prefixEnd) == needle.charAt(suffixEnd)) {
                prefixEnd++;
            }
            next[suffixEnd] = prefixEnd;
        }
    }
}
```

