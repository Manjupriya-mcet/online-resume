# online-resume
my first online resume
my map is not displayed
/*
This is empty on purpose! Your code to build the resume will go here.
 */

var bio = {
  "name" : "Manjupriya",
  "role" : "Web developer",
  "welcomeMessage" : "welcome to my resume",
  "biopic" : "https://s-media-cache-ak0.pinimg.com/originals/7f/a4/9e/7fa49e8b80d41fbcb94c12dab1fd28aa.jpg",
  "contacts" : {
    "mobile" : 9952723678,
    "email" : "manjurigha@gmail.com",
    "github" : "manjupriya-mcet",
    "location" : "TamilNadu"
  },
  "skills" : ["coding","developer","teamwork","HTML","CSS"]

};

var formattedRole = HTMLheaderRole.replace ("%data%", bio.role);
$("#header").prepend(formattedRole);
var formattedName = HTMLheaderName.replace ("%data%", bio.name);
$("#header").prepend(formattedName);
var formattedPic = HTMLbioPic.replace ("%data%", bio.biopic);
$("#header").append(formattedPic);

var formattedMobile = HTMLmobile.replace ("%data%", bio.contacts.mobile);
var formattedEmail = HTMLemail.replace ("%data%", bio.contacts.email);
var formattedGithub = HTMLgithub.replace ("%data%", bio.contacts.github);
var formattedLocation = HTMLlocation.replace ("%data%", bio.contacts.location);
var formattedContact = formattedMobile + formattedEmail + formattedGithub + formattedLocation;
$("#topContacts, #footerContacts").append(formattedContact);

var formattedMsg = HTMLwelcomeMsg.replace ("%data%", bio.welcomeMessage);
$("#header").append(formattedMsg);
$("#header").append(HTMLskillsStart);
for(var i = 0; i < bio.skills.length; i++) {
  $("#skills").append(HTMLskills.replace("%data%", bio.skills[i]));
}

/*if(bio.skills.length > 0)
{

  var formattedSkills = HTMLskills.replace ("%data%", bio.skills[0]);
  $("#skills").append(formattedSkills);
  formattedSkills = HTMLskills.replace("%data%",bio.skills[1]);
  $("#skills").append(formattedSkills);
  formattedSkills = HTMLskills.replace("%data%",bio.skills[2]);
  $("#skills").append(formattedSkills);
}*/

var work = {
  "jobs" : [
    {
      "employer" : "Infosys",
      "title" : "Trainee",
      "location" : "Mysore",
      "dates" : "In Progress",
      "description" : "I have been recruited by the Infosys in our College Campus Placement. Now I undertook the nanodegree program offered by Udacity and currently doing the Front End Web Developer course."
    }
  ]

};
function displayWork() {
for (var job = 0; job < work.jobs.length; job++ ) {
  $("#workExperience").append(HTMLworkStart);
  var formattedEmployer = HTMLworkEmployer.replace("%data%",work.jobs[job].employer);
  var formattedTitle = HTMLworkTitle.replace("%data%",work.jobs[job].title);
  var formattedEmployerTitle = formattedEmployer + formattedTitle;
  $(".work-entry:last").append(formattedEmployerTitle);
  var formattedLocation = HTMLworkLocation.replace("%data%",work.jobs[job].location);
  $(".work-entry:last").append(formattedLocation);
  var formattedDates = HTMLworkDates.replace("%data%",work.jobs[job].dates);
  $(".work-entry:last").append(formattedDates);
  var formattedDescription = HTMLworkDescription.replace("%data%",work.jobs[job].description);
  $(".work-entry:last").append(formattedDescription);
}
}
displayWork();
var projects = {
  "projects" : [
    {
      "title" : "Build a Portfolio",
      "dates" : "2016",
      "description" : "Helps to develop a responsive website that will display images, descriptions and links to each of the portfolio projects on all devices using bootstrap",
      "images": ["http://petapixel.com/assets/uploads/2013/07/thumbnails.jpg"]
    }
  ]
};
function displayProjects() {
  for(var project = 0; project < projects.projects.length; project++) {
    $("#projects").append(HTMLprojectStart);
    var formattedTitle = HTMLprojectTitle.replace("%data%",projects.projects[project].title);
    $(".project-entry:last").append(formattedTitle);
    var formattedDates = HTMLprojectDates.replace("%data%",projects.projects[project].dates);
    $(".project-entry:last").append(formattedDates);
    var formattedDescription = HTMLprojectDescription.replace("%data%",projects.projects[project].description);
    $(".project-entry:last").append(formattedDescription);
    var formattedImages = HTMLprojectImage.replace("%data%",projects.projects[project].images);
    $(".project-entry:last").append(formattedImages);

  }
}
displayProjects();

var education = {
  "schools" : [
    {
      "name" : "GVHSS",
      "location" : "TamilNadu",
      "degree" : "HSC",
      "dates" : "2010-2012",
      "majors" : ["Computer Science"],
      "url" : "images/fry.jpg"
    },
    {
      "name" : "MCET",
      "location" : "Pollachi",
      "degree" : "BE",
      "dates" : "2012-2016",
      "majors" : ["Engineering"],
      "url" : "images/fry.jpg"
    }
  ],
  "onlineCourses" : [
    {
      "title" : "Front End Web Developer",
      "school" : "Udacity",
      "dates" : "2016",
      "url" : "images/fry.jpg"

    }
  ]
};
function displayEducation() {
	for(var school = 0; school < education.schools.length; school++) {
		$("#education").append(HTMLschoolStart);

		var formattedSchoolName = HTMLschoolName.replace("%data%",education.schools[school].name);
		var formattedSchoolDegree = HTMLschoolDegree.replace("%data%",education.schools[school].degree);
    var formattedNameDegree = formattedSchoolName + formattedSchoolDegree;
    $(".education-entry:last").append(formattedNameDegree);

		var formattedSchoolDates = HTMLschoolDates.replace("%data%",education.schools[school].dates);
    $(".education-entry:last").append(formattedSchoolDates);

		var formattedSchoolLocation = HTMLschoolLocation.replace("%data%",education.schools[school].location);
    $(".education-entry:last").append(formattedSchoolLocation);

		var formattedSchoolMajor = HTMLschoolMajor.replace("%data%",education.schools[school].majors);
    $(".education-entry:last").append(formattedSchoolMajor);
   }

    $("#education").append(HTMLonlineClasses);
	  for(var onlineCourse = 0; onlineCourse < education.onlineCourses.length; onlineCourse++) {
      $("#education").append(HTMLschoolStart);

    var formattedTitle = HTMLonlineTitle.replace("%data%",education.onlineCourses[onlineCourse].title);
		var formattedSchool = HTMLonlineSchool.replace("%data%",education.onlineCourses[onlineCourse].school);
    $(".education-entry:last").append(formattedTitle + formattedSchool);
		var formattedDates = HTMLonlineDates.replace("%data%",education.onlineCourses[onlineCourse].dates);
    $(".education-entry:last").append(formattedDates);

		var formattedURL = HTMLonlineURL.replace("%data%",education.onlineCourses[onlineCourse].url);
    //$(".education-entry:last").append(formattedURL);
	}
};
displayEducation();


//you want to see a map?
$("#mapDiv").append(googleMap);
