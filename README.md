# CS F314 midterm: Rubric
Basic information

Name: Sarthak Chaudhary

BITS ID: 2019A7PS0125G

Email: f20190125@goa.bits-pilani.ac.in

Writing the exam from the hostel: N

## Question 1 (10 pts)
These are the points from the slides. If they list at least 3, give full points. They may also include accessibility or some other relevant point - judge yourself. Dock points if there are less than three, or they have written irrelevant points.
- Competitive, fluid vendor landscape
- Apps need to be multi-platform for wide adoption
- No “standard” device (iOS, Windows Phone devices?)
- Low bandwidth input (in most cases; what about tablets?)
- Limited screen size (tablets?)
- Unreliability in connectivity and device (network, power, ambient light, noise)
- Integration tradeoffs with cloud and enterprise services
## Question 2 (30 pts)
5 pt for identifying an accessibility issue and 5 for proposing a reasonable solution for each. Total (5+5)*3=30 pts.
There are the issues I can think of; if they list any other, please check with me first:
- color contrast on the search bar is low (5 pts): contrast should be improved (if the ratio 4.5:1 or 3.0:1 is specified, full points; if they talk about contrast but don't specify the ratio, 2 pts); can be tested using Accessibility scanner or automated testing (don't dock points if this bit is not mentioned)
- size of the "cheque" and the "mail" buttons is small (5 pts - if listed separately, give 5 pt each): the size should be at least 48x48 dp. (again, if the exact size is not mentioned, only 2 pts); can be tested using Accessibility scanner or automated testing (don't dock points if this bit is not mentioned)
- labels for any of the buttons (5 pt - make sure they point to the buttons clearly): provide appropriate labels; can be tested using Talk Back or other manual testing (should mention this; dock 1 pt if they don't)
## Question 3 (30 pts)
### Question 3.a (10 pts)
Any reasonable variant of the following should receive 10 pts; diagram is optional:
"This app lists the given states on the screen one by one and provides previous and next buttons to cycle through them in order"
### Question 3.b (10 pts)
Specifying JUnit or Espresso: 2 pts
Solution could look like
java
@Test
public void testPreviousGoaToRajasthan() {
    onView(withId(R.id.btn_prev)).perform(click());
    onView(withId(R.id.txt_show)).check(matches(withText("Rajasthan")));
}
- @Test annotation: 2 pts
- Reasonable nmae of the method: 2 pts
- Properly finding the btn_prev: 1 pts
- Properly performing click on it: 2 pts
- Properly finding the txt_show: 1 pt
- Properly writing the check(matches...) part: 2 pts
- Some students may also write a sentence or two confirming "Goa" is displayed first; unless it's total rubbish, ignore it, don't dock points
### Question 3.c (10 pts)
- Mention of rotation causing a recreation of the UI state: 2 pt
- Mention of creation of the new activity instance: 1 pt
- Stating that this is not an acceptable behavior: 2 pt
- Fixing this bu using a Bundle or a ViewModel: 5 pts
  - You may find answers that write elaborate code or some that simply explain in text. Both are fine, the Question did not specify code.
  - In either case, they should talk about what data they will put on the Bundle or the ViewModel: 3 pts
  - If they talk about Bundle, they should mention the onSaveInstanceState method: 2 pt
  - If they talk about the ViewModel, they should mention the setter/getter methods: 2 pt
## Question 4 (10 pts)
Stating they agree with the statement: 3 pts
Justification: 7 pts
- in the justification, you will see variants. Largely, they should talk about: decoupling, separation of concerns, keeping the code clean, better handling of lifecycles, etc. Give full points if they mention at least 3. 5 pts if only 2. 3 pts if only 1. 0 pts if none is mentioned.
## Question 5 (20 pts)
### 5.a (15 pts)
A reasonable description of:
- Recycler view and the item it holds: 8 pts, 4 each
- buttons for sorting: 3 pts
- floating action button for filtering: 2 pts
- then 2 pts for at least one of these
  - calendar menu bar button
  - the info on the title bar (dest/source cities and date and travellers info)
### 5.b (5 pts)
you can expect something like this:
java
@Dao
public interface FlightDao {
    @Insert  void insert(FlightEntry entry);

    @Query("SELECT * from flight_table ORDER BY price ASC")
    LiveData<List<FlightEntry>> getAllEntries();
}
- the insert query may or may not be shown
- @Query tag: 1 pt
- proper sql query: 2 pt
- proper written type of the method: 1 pt
- reasonable name of the method (e.g., getAllEntries): 1 pt
