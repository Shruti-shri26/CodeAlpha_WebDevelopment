# CodeAlpha_WebDevelopment
Creating a web-based Age Calculator using JavaScript to calculate users' ages based on their submitted date of birth, month, and year. JavaScript's built-in date and time functions simplify the age calculation process, making it easy to determine someone's age.


//CODE↓↓



<!DOCTYPE html>
<html>
<head>
  <title>Age Calculator</title>
</head>
<body>
  <h1>Enter your date of birth:</h1>
  <form>
    Date: <input type="text" id="date" name="date" required><br>
    Month: <input type="text" id="month" name="month" required><br>
    Year: <input type="text" id="year" name="year" required><br>
    <input type="button" value="Calculate Age" onclick="calculateAge()">
  </form>
  <h2 id="age"></h2>

  <script>
    function calculateAge() {
      var d1 = document.getElementById('date').value;
      var m1 = document.getElementById('month').value;
      var y1 = document.getElementById('year').value;

      var date = new Date();
      var d2 = date.getDate();
      var m2 = 1 + date.getMonth();
      var y2 = date.getFullYear();
      var month = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];

      if (d1 > d2) {
        d2 = d2 + month[m2 - 1];
        m2 = m2 - 1;
      }
      if (m1 > m2) {
        m2 = m2 + 12;
        y2 = y2 - 1;
      }
      var d = d2 - d1;
      var m = m2 - m1;
      var y = y2 - y1;

      document.getElementById('age').innerHTML = 'Your age is ' + y + ' years ' + m + ' months ' + d + ' days';
    }
  </script>
</body>
</html>