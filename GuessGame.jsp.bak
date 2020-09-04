<%@ page contentType="text/html; charset=utf-8" language="java"
	import="java.sql.*" errorPage=""%>
<!DOCTYPE HTML>
<html>
<head>
<meta charset="utf-8">
<title>Guess Game</title>
</head>
<body>
	Welcome to the Number Guess game.
	<p>I'm thinking of a number between 1 and 100.</p>
	<p>What's your guess???</p>
	<%
		String strSub = request.getParameter("submit");

		if (strSub == null)
		{
	%>
	<form name="guessGame" action="GuessGame.jsp" method="post">
		<input type="text" name="guessField"> <input type="submit"
			name="submit" value="Submit"> <input type="hidden" name="gc"
			value="1">
	</form>
	<%
		}
		else
		{
			boolean correctFlag = false;
			boolean higherFlag = false;
			int guessNumber = Integer
					.parseInt(request.getParameter("guessField"));
			int guessCount = Integer.parseInt(request.getParameter("gc"));

			int answer = 6987;

			if (guessNumber > answer)
			{
				higherFlag = true;
				correctFlag = false;
			}
			else if (guessNumber < answer)
			{
				higherFlag = false;
				correctFlag = false;
			}
			else
			{
				correctFlag = true;
			}
			if (correctFlag == false)
			{
	%>
	<form name="guessGame" action="GuessGame.jsp" method="post">
		<%
			if (higherFlag == true)
					{
						out.println(
								"Good guess, but nope. Try <B>lower</B>.You have made "
										+ guessCount + " guesses.");
						guessCount++;
					}
					else
					{
						out.println(
								"Good guess, but nope. Try <B>higher</B>.You have made "
										+ guessCount + " guesses.");
						guessCount++;
					}
		%>
		<input type="text" name="guessField"> <input type="submit"
			name="submit" value="Submit"> <input type="hidden" name="gc"
			value=<%=guessCount%>>
	</form>
	<%
		}
			else
			{
				out.println("Congratulations! You got it. And after just "
						+ guessCount + " tries.");
				out.println(
						"Care to <a href='GuessGame.jsp'>try again</a>?");
			}
		}
	%>
</body>
</html>
