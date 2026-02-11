# 🎀 Valentine's Quiz - Multi-Page Version - Setup Guide

## 📦 What's New

Your Valentine's website is now a **4-page interactive quiz** that builds up to the big question!

### **Page Flow:**
1. **Intro Page** - "Maa.. Here's a little Valentine's Day quiz for you"
2. **Multiple Choice** - "Who loves you the most?" (All answers are "wrong" → Answer: Everyone)
3. **Text Input** - "Ee prapancham lo andari kante evarante neeku ekkva ishtam?" (Accepts: Sagar, Maa, You)
4. **Valentine Proposal** - "Will you be my Valentine?" (Original evasive No button!)

---

## 🎨 Customizing Your GIFs

### **Find Your Pleading Puppy GIF (Page 4):**

1. Go to [Giphy.com](https://giphy.com)
2. Search for: **"puppy sad eyes"** or **"cute dog begging"**
3. Click on your favorite GIF → Click **Share** → Copy the **GIF Link**
4. In the HTML file, find line ~554:
   ```html
   <img id="mainGif" src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Pleading puppy">
   ```
5. Replace with your GIF URL

### **Find Your Celebration GIF (After Yes):**

1. On Giphy, search for: **"celebration dance"** or **"happy dance"**
2. Copy the GIF Link
3. Find line ~703:
   ```javascript
   mainGif.src = 'https://media.giphy.com/media/g9582DNuQppxC/giphy.gif';
   ```
4. Replace with your celebration GIF URL

---

## 🎮 How It Works

### **Page 1 - Introduction**
- Simple welcome message
- "Next" button to proceed
- Sets the romantic tone

### **Page 2 - Multiple Choice**
- Question: "Who loves you the most?"
- 3 buttons: Sagar, Lily, Aaryan
- **ANY button clicked** → Shows "Wrong! Answer: Everyone"
- Auto-advances to Page 3 after 2 seconds
- Buttons disable after clicking to prevent multiple clicks

### **Page 3 - Text Input**
- Question in Telugu: "Ee prapancham lo andari kante evarante neeku ekkva ishtam?"
- Text field for answer
- **Correct answers** (case-insensitive):
  - "Sagar"
  - "Maa"
  - "You"
- **Wrong answers** → Shows "Wrong! Correct Answer: Sagar"
- Auto-advances to Page 4 after 2 seconds (regardless of answer)
- Can press Enter key to submit

### **Page 4 - Valentine Proposal**
- Original evasive "No" button that jumps around
- "Yes" button triggers celebration
- GIF changes to celebration
- Confetti explosion
- Success message appears
- Back button hides when "Yes" is clicked

---

## ✨ Features Included

✅ **Progress Dots** - Shows which page you're on (4 dots at the top)  
✅ **Back Buttons** - Navigate to previous pages on all pages  
✅ **Auto-Advance** - Wrong answers show feedback, then move forward automatically  
✅ **Smart Text Matching** - Accepts variations like "sagar", "SAGAR", "Sagar"  
✅ **Mobile Responsive** - Works perfectly on phones  
✅ **Floating Hearts** - Background animation throughout  
✅ **Smooth Transitions** - Professional page transitions  
✅ **Enter Key Support** - Press Enter on text input to submit  

---

## 🧪 Testing Locally

1. **Download** the HTML file
2. **Open** it in your browser (double-click or drag-drop)
3. **Test the flow:**
   - Click "Next" on page 1
   - Try clicking each button on page 2
   - Try both correct and wrong answers on page 3
   - Test the "No" button evasion on page 4
   - Click "Yes" to see the celebration
4. **Test the Back buttons** - Make sure you can navigate backwards
5. **Test on mobile** - Transfer the file to your phone and test touch events

---

## 🚀 Deployment (Same as Before!)

### **Recommended: Netlify Drop (2 minutes)**

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the HTML file (and GIF files if using local)
3. Get your URL: `https://random-name.netlify.app`
4. Rename to: `https://maa-valentine-quiz.netlify.app` (or similar)
5. Share the link! 💕

### **Alternative: GitHub Pages**

1. Create GitHub account
2. New repository: `valentine-quiz`
3. Upload HTML file, rename to `index.html`
4. Settings → Pages → Deploy
5. URL: `https://yourusername.github.io/valentine-quiz/`

---

## 🎨 Customization Options

### **Change Page 1 Text:**
Find line ~496:
```html
<h1>Maa.. Here's a little Valentine's Day quiz for you 💕</h1>
```

### **Change Page 2 Buttons:**
Find lines ~506-508:
```html
<button class="choice-button" onclick="checkMultipleChoice('Sagar')">Sagar</button>
<button class="choice-button" onclick="checkMultipleChoice('Lily')">Lily</button>
<button class="choice-button" onclick="checkMultipleChoice('Aaryan')">Aaryan</button>
```

### **Change Page 3 Question:**
Find line ~518:
```html
<h2>Ee prapancham lo andari kante evarante neeku ekkva ishtam?</h2>
```

### **Change Accepted Answers (Page 3):**
Find line ~643:
```javascript
const correctAnswers = ['sagar', 'maa', 'you'];
```
Add or remove answers from this array!

### **Change Colors:**
Find the gradient backgrounds in the CSS:
- Line ~20: Initial gradient
- Line ~727: Celebration gradient

### **Adjust Auto-Advance Timing:**
Default is 2 seconds. To change:
- Page 2: Line ~621 → `setTimeout(() => { goToPage(3); }, 2000);`
- Page 3: Lines ~654 & 665 → `setTimeout(() => { goToPage(4); }, 2000);`
Change `2000` to any milliseconds (e.g., `3000` = 3 seconds)

---

## 📱 Mobile Optimization

The quiz is fully mobile-optimized with:
- Touch events for the "No" button
- Responsive text sizing
- Stacked buttons on small screens
- Touch-friendly input fields
- Proper viewport settings

---

## 🐛 Troubleshooting

### **Back button not working?**
- Make sure you're clicking the gray "Back" button, not browser back
- Each page should have a Back button except page 1

### **Text input not accepting answers?**
- Check capitalization doesn't matter: "Sagar" = "sagar" = "SAGAR"
- Whitespace is trimmed automatically
- Try pressing Enter instead of clicking Submit

### **No button not moving?**
- Only happens on Page 4
- Test with mouse hover (desktop) and tap (mobile)
- Make sure JavaScript is enabled

### **Page not advancing automatically?**
- Should auto-advance 2 seconds after showing feedback
- If stuck, use the Back button to navigate manually
- Check browser console for errors

---

## 🎯 Testing Checklist

Before sharing:
- [ ] Downloaded/uploaded HTML file
- [ ] Customized both GIF URLs (optional)
- [ ] Tested Page 1 → Next button works
- [ ] Tested Page 2 → All 3 buttons show "Wrong" and advance
- [ ] Tested Page 3 → Correct answers work ("Sagar", "Maa", "You")
- [ ] Tested Page 3 → Wrong answers show correct answer and advance
- [ ] Tested Page 4 → No button jumps away
- [ ] Tested Page 4 → Yes button triggers celebration
- [ ] Back buttons work on all pages
- [ ] Tested on mobile device
- [ ] Deployed to hosting service
- [ ] Live URL works
- [ ] Ready to share! 💕

---

## 💡 Pro Tips

1. **Test the full flow** - Go through all pages yourself first
2. **Screenshot backup** - Take screenshots in case the link fails
3. **Perfect timing** - Send when she has time to go through all pages
4. **Watch her reaction** - The build-up makes the proposal more fun!
5. **Have fun** - The playful quiz makes it memorable

---

## 🎊 What Makes This Special

The multi-page format:
- ✨ **Builds anticipation** - Each page leads to the next
- 💕 **Shows effort** - More thought than a single question
- 😄 **Makes her smile** - Playful wrong answers add humor
- 🎯 **Personal touch** - Questions specific to your relationship
- 🎉 **Big finale** - The evasive button is the grand finale

---

## 🆘 Need Help?

Common questions:

**Q: Can I add more questions?**
A: Yes! Copy one of the existing page divs and modify it. Update the progress dots and navigation.

**Q: Can I remove the Back buttons?**
A: Yes! Remove the "Back" button HTML and adjust the `goToPage()` calls.

**Q: Can I skip the auto-advance?**
A: Yes! Remove the `setTimeout()` calls and add "Next" buttons instead.

**Q: Can I change the correct answers?**
A: Yes! Edit the `correctAnswers` array on line ~643.

---

**Good luck with your Valentine's quiz! The multi-page format makes it extra special! 🎀💕**
