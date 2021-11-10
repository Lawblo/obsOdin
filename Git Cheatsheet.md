# [[Git]] Cheatcheet:
#git
This is a reference list of the most commonly used Git commands.

#### Commands related to a remote repository:
<pre>git clone git@github.com:USER-NAME/REPOSITORY-NAME.git</pre>
<pre>git push or git push origin main (Both accomplish the same goal in this context)</pre>

#### Commands related to workflow:
<pre>git add .</pre>
<pre>git commit -m "A message describing what you have done to make this snapshot different"</pre>

#### Commands related to checking status or log history
<pre>git status</pre>
<pre>git log</pre>

#### Basic Git syntax
<pre>program | action | destination.</pre>
For example,
#### Ex. 1:
<pre>git add . </pre>
is read as
<pre>git | add | .</pre>
where the period represents everything in the current directory
#### Ex. 2: 
<pre>git commit -m "message"</pre> 
is read as
<pre>git | commit -m | "message";</pre>
#### Ex. 3:
<pre>git status</pre> 
is read as 
<pre>git | status | (no destination).</pre>