This is an extremely simple, lightweight resume custom resume template. Its main feature is that it allows you to modularly define items in your resume, and then dynamically reorder or only include certain ones based on a config variable - letting you easily create resumes of the same resume.

## Motivation

I created this to tackle a problem I had this year. For certain types of jobs, I wanted to submit slightly different resume variations - for example, when applying to a security job I wanted to put security experience, but for an aerospace job I wanted to mention a certain personal project. My only options were either to a) create separate copies of each resume with slight changes (multiplying the amount of work to keep all of them up to date), or b) Remember to comment and uncomment certain lines in LaTeX (which is tedious and error prone). I wanted to create something that would let me change a single variable and have the resume "rewrite itself." Moreover, most of the resume templates I found online were bloated and overly complex.

## Usage

This template lets you very easily define modules, where each module is a resume item (work experience, education item, etc). These modules can then be really easily reordered by defining separate layouts, with a simple syntax:

For example, let's say in the simplest case I want to have two versions of my resume with the same education section, but with my projects in a different order. I can write out this code:

```latex
\newif\ifresumeA
\newif\ifresumeB

\resumeAtrue
\resumeBfalse

\rsec{Education}

\ifresumeA
  \rsec{Project 1}
  \rsec{Project 2}
\fi

\ifresumeB
  \rsec{Project 2}
  \rsec{Project 1}
\fi
```

Now, by setting resumeAtrue and resumeBfalse or vice versa, I can really quickly change the order in the version rendered.

Of course, this can be extended to be much more complex. See the example resume (example.tex) for more details.
