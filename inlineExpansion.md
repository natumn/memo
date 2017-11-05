##インライン展開とは
 コンパイラの最適化のの手法の一つで、関数呼び出しを行う際、関数のコード展開を行い、関数よびだしにかかるオーバーヘッド（制御転送）を削減する。
##例 
 int pred(int x) {
	 if ( x==0 ) return 0;	 
	 else return x - 1;
 }

###インライン展開前
 int f(int y) {
	 return pred(y) + pred(0) + pred(y + 1);	 
 }

###インライン展開後
 int f(int y) {
	 int temp 0;
	 if (y       == 0) temp += 0; else temp += y       - 1;
   if (0       == 0) temp += 0; else temp += 0       - 1;
   if ((y + 1) == 0) temp += 0; else temp += (y + 1) - 1;
   return temp;	
 }

###メリッド、デメリッド

め：早くなる。
で：コードサイズが大きくなるので、組み込みなどはあまり使用できない。

