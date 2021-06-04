public class Solution {
    public static String[] solution(String[] l) {
    	String[][] matrix=new String[l.length][10];
    	 for(int i=0;i<l.length;i++)
    	 {
    		 matrix[i]=l[i].split("\\.",0);		//here we split the string array and put it in string matrix without '.'
    	 }
    	 int max=0;
    	 for(int i=0;i<matrix.length;i++)
    		 for(int j=0;j<matrix[i].length;j++)
    		 {
    			 if(matrix[i].length>max)
    				 max=matrix[i].length;		//the longest string[] in matrix
    		 }
    	 String[][] res=new String[matrix.length][max];
    	 for(int i=0;i<matrix.length;i++)
    		 for(int j=0;j<matrix[i].length;j++)
    		 {
    			 res[i][j]=matrix[i][j];		//I copied matrix into new Matrix res, and changes the null
    		 }									//pointers in res to point to -1, so that we can prioritize longer strings
    	 for(int i=0;i<res.length;i++)			//(2.0.0 comes after 2.0, when compared, 2 and 2, 0 and 0, 0 and -1.
    		 for(int j=0;j<res[i].length;j++)
    		 {
    			 if(res[i][j]==null)
    				 res[i][j]="-1";
    		 }
    	 for(int i=0;i<res.length;i++)
    	 {
    		 for(int j=0;j<res.length;j++)
    		 {
    			for(int k=0;k<res[i].length;k++)
    			{
       			 if(res[i][k]!=null && res[j][k]!=null)
       			 {
       				 double One=Double.parseDouble(res[i][k]);		// parse to double members of res Matrix so that we can compare them
       				 double Two=Double.parseDouble(res[j][k]);		// one to another
       			 
       				 if(One>Two)
       				 {
       					 String[] tmp=matrix[i];					//res members and matrix members keep the same order(example, 1 1 1 and then 2 0)
       					 matrix[i]=matrix[j];						//in matrix, and in res that would be(1 1 1 and then 2 0 -1)
       					 matrix[j]=tmp;								//we stored the original(example 1.1.1-> 1 1 1) member to one row of res and matrix
       					 String[] temp=res[i];						//so that we can compare them by the columns(example 2 0 -1 and 2 0 0,
       					 res[i]=res[j];								// 2 and 2, 0 and 0, -1 and 0), that we cacn arhieve by triple for loop, two for 
       					 res[j]=temp;								//members we need to compare, and third for loop for each char of those members 
       					 break;										//we can then compare parts with equal prioritisation with each other.
       				 }												//one more time, res and matrix keep the same order of members and we can use that to
       				 if(One<Two)									//sort res and matrix in the same time, keeping the null members of matrix
       				 {												//(they aren't affected by the change in the Matrix res(null->-1))
       					 break;
       				 }
       				 }
       			 }
    			}
    		 }
    	 
	 String[] result=new String[l.length];
	 for(int i=0;i<result.length;i++)
	 {
		 result[i]="";									
	 }
	 for(int i=0;i<matrix.length;i++)
		 for(int j=0;j<matrix[i].length;j++)
		 {
			 result[i]=result[i]+matrix[i][j];
			 if(matrix[i].length>1 && j<matrix[i].length-1)				//matrix rows(original l members) are placed into new String array
				 result[i]=result[i]+".";								//we add dots to the positions they were in originally
		 }
	 for (int i = 0; i < result.length / 2; i++) {
	        String temp = result[i];
	        result[i] = result[result.length - 1 - i];				//reverse result string[]
	        result[result.length - 1 - i] = temp;
	 }
	 for(int i=0;i<result.length;i++)
	 {
		 l[i]=result[i];								
	 }
    return l;
    }
}
