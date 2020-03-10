# iOSPT Demo Day

## Requirements

1. Fork and clone the repository
2. **Add your presentation content**
    1. Slide deck (4 required slides)
    2. Links
    3. Answer all questions 
    4. YouTube demo video (1-2 min max)
3. Polish your Github Code repository
    1. Add screenshots and an overview to your GitHub Code Repository
    2. You should make that repository the "Public Portfolio" for your project
    3. Look at [John Sundell's Splash project](https://github.com/JohnSundell/Splash) for inspiration (code, images, GIFs)
4. Create a pull request (PR) and **tag your TL and Instructor**

## Links

* Github Code: `<insert Github repository link here>`
* Github Proposal: `<insert Proposal Pull Request here>`
* Trello/Github Project Kanban: `<insert trello board here>`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `<insert video url here>`

## Hero Image

`<Post one screenshot in an iPhone Simulator frame or an iPhone 11 Pro render using placeit.com>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    the Graph was one of my favorite features implemented because it's a cool visual to have and to see it get updated is nice to have in a app.

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    A Theme Helper, tried it first using Protocols and Delegates. Since it was multiple VC's that needed to get updated I researched and learned that NSNotification and Observers could be a better solution. But that also brought me issues because I couldn't figure out how to have Multiple Observers listening to the same '.post' . So my soulution was UserDefaults, and having a function in each view to check which UserDefault was chosen and update the background color accordingly.
  
3. Share a chunk of code (or file) you're proud of and explain why.

   class ThemeSelectionViewController: UIViewController {
    
    var themeHelper: ThemeHelper?

    @IBOutlet weak var darkThemeBtn: UIButton!
    @IBOutlet weak var lightThemeBtn: UIButton!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        darkThemeBtn.layer.cornerRadius = 5.0
        lightThemeBtn.layer.cornerRadius = 5.0

    }
    
    @IBAction func darkThemeBtnTapped(_ sender: Any) {
        themeHelper?.setThemePreferenceToDark()
        let name = Notification.Name(rawValue: themeHelper?.themePreference ?? .darkNotificationKey)
        NotificationCenter.default.post(name: name, object: nil)
        dismiss(animated: true, completion: nil)
    }
    
    
    @IBAction func whiteThemeBtnTapped(_ sender: Any) {
        themeHelper?.setThemePreferenceToWhite()
        let name = Notification.Name(rawValue: themeHelper?.themePreference ?? .lightNotificationKey)
        NotificationCenter.default.post(name: name, object: nil)
        dismiss(animated: true, completion: nil)
    }
    
}

Seems very simple but this code took me a lot of work to figure out to work properly, and to achieve it made me proud
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    What mood are you feeling right now, you can pull out your phone and open the app and simply tap on the mood you're feeling. Then add a comment as to why you feel this way or what made you feel this way. We will then show you a nice motivational quote to give you a little motivation or something to reflect on. Then you will see a list of all the moods you have chosen in the past.
  
5. What is your #1 feature?

    I believe the best feature is hard to pick because we have great ones, but I will have to pick the Graph that also gets updated as you're picking a mood.
  
6. What are you future goals?

    Polish up the UI, add sign in option to track your moods and comments connected to the mood.

## Required Slides (Add your Keynote to your PR)

1. App Name / Team Slide
2. Elevator Pitch
3. Your #1 Feature (Customer facing — what can I do with your app?)
4. Future Goals

## Slide Requirements

1. 50 pt font minimum
2. Be concise — don't write sentences/paragraphs (put these in your slide notes for speaking)
3. 3-6 bullets maximum per slide
4. Do the squint test (can you read the text if you squint, if so, make the font bigger)
6. Images are always welcome
7. Do the Grandma Test (Would your Grandma understand you?)

### Optional Slides

1. Blooper: What's a funny bug or blooper? (screenshots/GIFs please)
2. Revenue Model: If the app was your sole source of income, how would you monetize it?

## Presentation Format

**7 minutes/team**

* 4 minute presentation (5 minute hard cap)
* 3 minutes of questions

We have ~12 teams presenting today — please practice your presentation with a timer (as a team), and make sure you fit within the time limit.

Plan on having one person present the slides and live demo. Please practice your presentation in front of a mirror or with your team 2-5 times. Have the app running and visible (Simulator or QuickTime) so you can quickly transition between slides and live demo.

* App Name / Team Slide (30 seconds)
* Elevator Pitch Slide (30 seconds)
* Your #1 Feature (30 seconds)
* Live Demo (2 minutes)
* Future Goals (30 seconds)
* Questions (3 minutes)
