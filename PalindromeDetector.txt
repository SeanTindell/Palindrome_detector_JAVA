package sean.tindell.sparc.test;

import java.text.SimpleDateFormat;  
import java.util.Calendar;  
import java.util.Date;  
import java.util.Set;  
import java.util.TreeSet; 

public class PalindromeDetector 
{
    public static Set<Date> getPalindromeDates(Date start, Date end)
    {
    	Set<Date> dates = new TreeSet<Date>();  
    	
    	SimpleDateFormat formattedDate = new SimpleDateFormat("MMddyyyy");
    	Calendar beginDate = Calendar.getInstance();
    	Calendar endDate = Calendar.getInstance();
    	
    	beginDate.setTime(start);
    	endDate.setTime(end);
    	
    	while(beginDate.compareTo(endDate) <= 0)
    	{
    		
    		String original = formattedDate.format(beginDate.getTime()).toString();    		
    		String reverse = "";
  	      	int length = original.length();
  	      
    		for(int i = length - 1; i >= 0; i--)
    			reverse = reverse + original.charAt(i);
  	      
    		if (original.equals(reverse))
    		{
  	 		  	dates.add(beginDate.getTime());
  	 		  	
  	 	  	}
  	 	  
  	 	  beginDate.add(Calendar.DATE, 1);
    	}
    	
			return dates;
  
    }

}

