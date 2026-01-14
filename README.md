# CTAT Logic Rule Firing Tutor

An intelligent tutoring system built with Carnegie Mellon's CTAT (Cognitive Tutor Authoring Tools) for teaching forward-chaining logic rule firing.

## 📋 Overview

This project implements a complete educational system for teaching students how logical rules fire in forward-chaining inference systems. Students learn to:
- Identify which rules can fire based on current facts
- Determine the correct firing sequence when multiple rules are applicable
- Deduce new facts from fired rules
- Understand preconditions and logical dependencies

## 🎯 Features

### Problem 1: Sequential Rule Firing
- **Simple linear chain**: R1 → R2 → R3
- **Single solution path**: Teaches basic concepts
- **Rules**:
  - R1: A → B
  - R2: B → C
  - R3: C → D

### Problem 2: Complex Multi-Path Reasoning
- **Parallel rule execution**: Multiple valid orderings
- **4+ solution paths accepted**: Any correct sequence is valid
- **Complex dependencies**: Rule R5 requires both E and D
- **Rules**:
  - R1: A → B
  - R2: A → C
  - R3: C → D
  - R4: B → E
  - R5: E and D → F

## ✨ Intelligent Features

### Three-Level Hint System
1. **General hint**: Guides thinking about the current situation
2. **Specific hint**: Provides direction toward the solution
3. **Bottom-out hint**: Gives exact answer when needed

### Comprehensive Error Detection
- **Precondition violations**: Detects attempts to fire rules before preconditions are satisfied
- **Wrong fact deductions**: Identifies incorrect conclusions from rule firing
- **Contextual feedback**: Explains *why* an action is incorrect

### Example Error Messages
```
❌ "Rule R3 cannot fire because its precondition C is not yet true. 
    You need to fire a rule that deduces C first."

❌ "Rule R5 requires both E and D to be true. E has not been deduced yet."

❌ "Rule R1 is 'A → B', so it deduces B, not C. 
    Check the right-hand side of the rule."
```

## 🚀 Getting Started

### Prerequisites
- CTAT HTML5 Library (download from https://ctat.pact.cs.cmu.edu/)
- Modern web browser (Chrome, Firefox, Edge, Safari)
- Basic understanding of propositional logic

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/CTAT-Logic-Tutor.git
   cd CTAT-Logic-Tutor
   ```

2. **Download CTAT Library**
   - Visit https://ctat.pact.cs.cmu.edu/
   - Download CTAT HTML5 Library
   - Extract to a `CTAT/` folder in project root

3. **Update file paths** (if needed)
   - Open `problem1.html` and `problem2.html`
   - Verify CTAT library paths point to your CTAT folder

4. **Open in browser or CTAT**
   - **Option A**: Open HTML files directly in browser (limited functionality)
   - **Option B**: Use CTAT Behavior Recorder for full features

### Quick Start Without CTAT Installation

The problems will work in basic mode without CTAT, but won't provide:
- Step-by-step guidance
- Hint buttons
- Progress tracking
- Detailed feedback

## 📖 Usage

### Problem 1 Solution
```
First fired rule: R1    →    Deduced fact: B
Second fired rule: R2   →    Deduced fact: C
Third fired rule: R3    →    Deduced fact: D
```

### Problem 2 Valid Solutions

**Solution 1:**
```
R1 → B    R4 → E    R2 → C    R3 → D    R5 → F
```

**Solution 2:**
```
R1 → B    R2 → C    R4 → E    R3 → D    R5 → F
```

**Solution 3:**
```
R1 → B    R2 → C    R3 → D    R4 → E    R5 → F
```

**Solution 4:**
```
R2 → C    R1 → B    R3 → D    R4 → E    R5 → F
```

...and more valid combinations!

## 🏗️ Project Structure

```
CTAT-Logic-Tutor/
├── README.md                 # This file
├── problem1.html             # Problem 1 student interface
├── problem1.brd              # Problem 1 behavior graph
├── problem2.html             # Problem 2 student interface
├── problem2.brd              # Problem 2 behavior graph (4 solution paths)
├── styles.css                # Shared stylesheet
└── docs/                     # Additional documentation
```

## 🛠️ Technical Details

### Behavior Graph (.brd files)
- **XML-based state machine** defining tutor behavior
- **Nodes**: Represent states in the problem-solving process
- **Edges**: Define valid transitions and student actions
- **Matchers**: Specify acceptable inputs
- **Messages**: Provide feedback, hints, and success messages

### Key Technologies
- **CTAT Framework**: Carnegie Mellon's intelligent tutoring system
- **Example-Tracing Tutors**: Model-based tutoring approach
- **HTML5/CSS3**: Modern web interface
- **XML**: Behavior graph definition

### Error Detection Implementation
The system tracks:
1. **Current knowledge state**: Which facts have been deduced
2. **Rule preconditions**: What must be true for each rule to fire
3. **Rule consequents**: What each rule deduces
4. **Student actions**: Compares against valid state transitions

## 📊 Educational Research Basis

This tutor implements principles from:
- **Cognitive Load Theory**: Progressive difficulty, scaffolding
- **Immediate Feedback**: Real-time error detection
- **Worked Examples**: Multiple solution paths demonstrated
- **Metacognitive Support**: Three-level hints encourage self-reflection

## 🤝 Contributing

Contributions welcome! Ideas for enhancement:
- [ ] Add more complex problems with disjunctions
- [ ] Implement backward-chaining logic tutors
- [ ] Add visualization of fact knowledge base
- [ ] Create assessment/grading module
- [ ] Multi-language support

## 📝 License

This project is educational material. Free to use for academic purposes.

## 👥 Authors

- **Your Name** - Initial work - [YourGitHub](https://github.com/YOUR-USERNAME)

## 🙏 Acknowledgments

- Carnegie Mellon University for CTAT framework
- Course instructor for project requirements
- CTAT community for documentation and support

## 📧 Contact

Questions? Open an issue or contact: your.email@example.com

---

**Note**: This is a student project for Technology-Enhanced Adaptive Learning course.
