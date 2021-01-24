<template lang="pug">
section.skills
	.skills__inner
		header.skills__header
			h2.skills__title My Skills
			p.skills__description I dabble in the following technologies and software.
			p.skills__description Click the skills for more information.
		.skills__items
			SkillsItem(v-for="(item,i) in skills" :item="item" :key="i")

</template>

<script>
import SkillsItem from '@/components/SkillsItem.vue'

export default {
	name: 'Skills',
	components: {
		SkillsItem
	},
  data() {
		return {
			skills: [
				{
					id: 1,
					title: 'HTML5',
					modal: {
						description: 'I can write semantic HTML5 in my sleep. HTML5 is the latest evolution of the standard that defines HTML. The term represents two different concepts. It is a new version of the language HTML, with new elements, attributes, and behaviors, and a larger set of technologies that allows the building of more diverse and powerful Web sites and applications. This set is sometimes called HTML5 & friends and often shortened to just HTML5.',
						source: '[Source]',
						sourceHref: 'https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5'
					}
				},
				{
					id: 2,
					title: 'CSS3',
					modal: {
						description: 'CSS3 is the latest evolution of the Cascading Style Sheets language and aims at extending CSS2.1. It brings a lot of long-awaited novelties, like rounded corners, shadows, gradients, transitions or animations, as well as new layouts like multi-columns, flexible box or grid layouts. Experimental parts are vendor-prefixed and should either be avoided in production environments, or used with extreme caution as both their syntax and semantics can change in the future.',
						source: '[Source]',
						sourceHref: 'https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3'
					}
				},
				{
					id: 3,
					title: 'Sass',
					modal: {
						description: 'I love Sass. It\'s a powerful tool in any front-end developer\'s arsenal. ass is a scripting language that is interpreted or compiled into Cascading Style Sheets (CSS). SassScript is the scripting language itself. Sass consists of two syntaxes. The original syntax, called "the indented syntax", uses a syntax similar to Haml. It uses indentation to separate code blocks and newline characters to separate rules. The newer syntax, "SCSS", uses block formatting like that of CSS. It uses braces to denote code blocks and semicolons to separate lines within a block. The indented syntax and SCSS files are traditionally given the extensions .sass and .scss, respectively.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Sass_(stylesheet_language)'
					}
				},
				{
					id: 4,
					title: 'Gulp',
					modal: {
						description: 'I can read a Gulp file and tell you exactly what it is doing and where it is putting your compiled files. Need a new task? I can create and implement new tasks based on Node.Js package manager (npm) to create a seamless workflow. Gulp is a toolkit for automating painful or time-consuming tasks in your development workflow, so you can stop messing around and build something.',
						source: '[Source]',
						sourceHref: 'https://gulpjs.com/'
					}
				},
				{
					id: 5,
					title: 'Node.js',
					modal: {
						description: 'I\'m familiar with Node.js and how I use it to implement workflows with npm and Gulp. While I know a little about Node.js, I\'m certainly no expert. Node.js® is a JavaScript runtime built on Chrome\'s V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js\' package ecosystem, npm, is the largest ecosystem of open source libraries in the world.',
						source: '[Source]',
						sourceHref: 'https://nodejs.org/'
					}
				},
				{
					id: 6,
					title: 'JavaScript',
					modal: {
						description: 'I use JavaScript mostly for Front-End and User Experience purposes. For example, a pop-up modal with additional information without having to navigate to a new page or to iterate the same element multiple times and many other uses. I\'m constantly learning vanilla JavaScript and new ways to implement it. JavaScript (JS) is a lightweight interpreted or JIT-compiled programming language with first-class functions. While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat. JavaScript is a prototype-based, multi-paradigm, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles. Read more about JavaScript.',
						source: '[Source]',
						sourceHref: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript'
					}
				},
				{
					id: 7,
					title: 'ES6+',
					modal: {
						description: 'ES6 is one of the newest, stable versions of the JavaScript language. As the language evolves, it gets easier to write with a simplified syntax. I\'m all over ES6. I\'m getting more and more familiar with the syntax and enjoy writing the ease of writing it compared to older standards. ECMAScript 2015 (ES6) is the sixth edition of the ECMAScript Language Specification standard. It defines the standard for the JavaScript implementation in SpiderMonkey, the engine used in Firefox and other Mozilla applications.',
						source: '[Source]',
						sourceHref: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_2015_support_in_Mozilla'
					}
				},
				{
					id: 8,
					title: 'Babel',
					modal: {
						description: 'I can Babel. In fact, it is the exact same syntax as ES6. Babel is a transpiler for JavaScript best known for its ability to turn ES6 (the next version of JavaScript) into code that runs in your browser (or on your server) today.',
						source: '[Source]',
						sourceHref: 'https://codemix.com/blog/why-babel-matters/'
					}
				},
				{
					id: 9,
					title: 'React',
					modal: {
						description: 'ReactJS is my latest adventure in front-end development. I have a solid understanding of the overall concept of ReactJS and have the ability to code one page applications from scratch. I\'ve been learning more and more about state management and how important it is to dynamic applications. Check out some of my ReactJS projects on GitHub or CodePen.',
						source: '[Source]',
						sourceHref: 'https://reactjs.org/'
					}
				},
				{
					id: 10,
					title: 'jQuery',
					modal: {
						description: 'I can write jQuery fairly well, however, in my quest for website optimization and speed, I have resorted to writing vanilla JavaScript in place of jQuery. The size and scope of my projects don\'t have the need to rely on jQuery\'s entire library. I have found writing vanilla JavaScript is lighter. jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers. With a combination of versatility and extensibility, jQuery has changed the way that millions of people write JavaScript.',
						source: '[Source]',
						sourceHref: 'https://jquery.com/'
					}
				},
				{
					id: 10,
					title: 'jQuery',
					modal: {
						description: 'I can write jQuery fairly well, however, in my quest for website optimization and speed, I have resorted to writing vanilla JavaScript in place of jQuery. The size and scope of my projects don\'t have the need to rely on jQuery\'s entire library. I have found writing vanilla JavaScript is lighter. jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers. With a combination of versatility and extensibility, jQuery has changed the way that millions of people write JavaScript.',
						source: '[Source]',
						sourceHref: 'https://jquery.com/'
					}
				},
				{
					id: 11,
					title: 'Responsive Web Design',
					modal: {
						description: 'Responsive Web Design creates an optimal user experience for all users no matter what device they\'re using. Responsive Web Design is essential to any website if you want your users to be happy. Responsive Web Design, originally defined by Ethan Marcotte in A List Apart, responds to the needs of the users and the devices they\'re using. The layout changes based on the size and capabilities of the device. For example, on a phone users would see content shown in a single column view; a tablet might show the same content in two columns.',
						source: '[Source]',
						sourceHref: 'https://developers.google.com/web/fundamentals/design-and-ux/responsive/'
					}
				},
				{
					id: 12,
					title: 'Git',
					modal: {
						description: 'Git is essential to keeping track of the changes made to your projects. I typically use Git from the Command Line Interface (CLI) with the use of GitHub. Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.',
						source: '[Source]',
						sourceHref: 'https://git-scm.com/'
					}
				},
				{
					id: 13,
					title: 'MVC',
					modal: {
						description: 'I\'m familiar with the MVC and how it works. I recently dabbled in MVC while building web applications within the ASP.NET framework using C# and Angular. The Model–view–controller (MVC) is a software architectural pattern for user interfaces that divides an application into three interconnected parts. This is done to separate internal representations of information from the ways information is presented to, and accepted from, the user. The MVC design pattern decouples these major components allowing for efficient code reuse and parallel development.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller'
					}
				},
				{
					id: 14,
					title: 'macOS',
					modal: {
						description: 'I am well-versed in macOS. In fact, it is my weapon of choice for operating systems. However, it is getting hard to see through all of the emojis (still better than Windows). I can still fix most issues that are macOS software related. macOS is the current series of Unix-based graphical operating systems developed and marketed by Apple Inc. designed to run on Apple\'s Macintosh computers ("Macs"). It has been preinstalled on all Macs since 2002. Within the market of desktop, laptop and home computers, and by web usage, it is the second most widely used desktop OS, after Microsoft Windows.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/MacOS'
					}
				},
				{
					id: 15,
					title: 'Adobe CC',
					modal: {
						description: 'My weapons of choice are Photoshop and Illustrator. I\'m familiar with most applications in the Adobe Creative Cloud. More specifically, I\'m proficient in Photoshop, Illustrator, InDesign, Dreamweaver, TypeKit, Adobe XD, Acrobat Professional and Muse. I have experience with Premiere, After Effects, Stock, and Lightroom. Adobe Creative Cloud is a set of applications and services from Adobe Systems that gives subscribers access to a collection of software used for graphic design, video editing, web development, photography, along with a set of mobile applications and also some optional cloud services. In Creative Cloud, a monthly or annual subscription service is delivered over the Internet.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Adobe_Creative_Cloud'
					}
				},
				{
					id: 16,
					title: 'Photoshop',
					modal: {
						description: 'I use Photoshop for photo manipulation and optimizing web graphics. Adobe Photoshop is a raster graphics editor developed and published by Adobe Systems for macOS and Windows.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Adobe_Photoshop'
					}
				},
				{
					id: 17,
					title: 'Illustrator',
					modal: {
						description: 'I use Illustrator for creating and editing vector graphics. Adobe Illustrator is a vector graphics editor developed and marketed by Adobe Systems. The latest version, Illustrator CC 2018, is the 22nd generation in the product line.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Adobe_Illustrator'
					}
				},
				{
					id: 18,
					title: 'Sketch',
					modal: {
						description: 'I use Sketch for UI design and page layouts. Everyone once in awhile, I will use it for creating and editing vector graphics. Sketch is a proprietary vector graphics editor for Apple\'s macOS, developed by the Dutch company Bohemian Coding. It won an Apple Design Award in 2012. Sketch was first released on 7 September 2010.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Sketch_(application)'
					}
				},
				{
					id: 19,
					title: 'Terminal',
					modal: {
						description: 'I use Terminal to play with Node.js, start my Gulp workflow, use Git for version control, and sometimes reset a password or find REAL information about my computer and its file system. Terminal provides text-based access to the operating system, in contrast to the mostly graphical nature of the user experience of macOS, by providing a command line interface (CLI) to the operating system when used in conjunction with a Unix shell, such as bash (the default shell in Mac OS X Jaguar and later).',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Terminal_(macOS)'
					}
				},
				{
					id: 20,
					title: 'Windows 10',
					modal: {
						description: 'I don\'t mind Windows 10. I know my way around it quite well. It\'s a nice escape from macOS when the emojis get in the way, but I prefer a Mac. Windows 10 is a personal computer operating system developed and released by Microsoft as part of the Windows NT family of operating systems. It was released on July 29, 2015. It is the first version of Windows that receives ongoing feature updates.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Windows_10'
					}
				},
				{
					id: 21,
					title: 'Visual Studio',
					modal: {
						description: 'It\'s fat. It\'s bloated. It makes my Windows machine not respond... often. However, depending on the size and scope of the project, it is very useful and does a lot of work for you. I use Visual Studio when I\'m working on apps that are built in C# and Angular. Microsoft Visual Studio is an integrated development environment (IDE) from Microsoft. It is used to develop computer programs, as well as web sites, web apps, web services and mobile apps.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Microsoft_Visual_Studio'
					}
				},
				{
					id: 22,
					title: 'Visual Studio Code',
					modal: {
						description: 'Visual Studio Code is what all the cool kids are using these days. I imagine I will eventually switch. I occasionally use it when Atom is giving me grief. Visual Studio Code is a source code editor developed by Microsoft for Windows, Linux and macOS. It includes support for debugging, embedded Git control, syntax highlighting, intelligent code completion, snippets, and code refactoring.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Visual_Studio_Code'
					}
				},
				{
					id: 23,
					title: 'Linux',
					modal: {
						description: 'The more I use the Linux command line interface, the more I like it. You’ve probably heard mention of the Linux command line. This is the shell – a command process that allows you to control the computer via commands typed into a text interface. This is what, at one time, scared people away from Linux the most (assuming they had to learn a seemingly archaic command line structure to make Linux work).',
						source: '[Source]',
						sourceHref: 'https://www.linux.com/what-is-linux'
					}
				},
				{
					id: 24,
					title: 'WordPress',
					modal: {
						description: 'I can create custom WordPress themes from scratch and implement them in the framework of your choice. I like to use WordPress for freelance clients so they are able to manage their own online presence. WordPress is a free and open-source content management system (CMS) based on PHP and MySQL.[4] To function, WordPress has to be installed on a web server, which would either be part of an Internet hosting service or a network host in its own right.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/WordPress'
					}
				},
				{
					id: 25,
					title: 'Bootstrap',
					modal: {
						description: 'Bootstrap is a great framework to get started fast and develop responsive websites or web applications. Bootstrap is a free and open-source front-end web framework for designing websites and web applications. It contains HTML- and CSS-based design templates for typography, forms, buttons, navigation and other interface components, as well as optional JavaScript extensions. Unlike many web frameworks, it concerns itself with front-end development only.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework)'
					}
				},
				{
					id: 26,
					title: 'Foundation',
					modal: {
						description: 'A Framework for any device, medium, and accessibility. Foundation is a family of responsive front-end frameworks that make it easy to design beautiful responsive websites, apps and emails that look amazing on any device. Foundation is semantic, readable, flexible, and completely customizable.',
						source: '[Source]',
						sourceHref: 'https://foundation.zurb.com/'
					}
				},
				{
					id: 27,
					title: 'User Experience',
					modal: {
						description: 'User experience encompasses all aspects of the end-user\'s interaction with the company, its services, and its products.',
						source: '[Source]',
						sourceHref: 'https://www.nngroup.com/articles/definition-user-experience/'
					}
				},
				{
					id: 28,
					title: 'UI Design',
					modal: {
						description: 'User interface design (UI) or user interface engineering is the design of user interfaces for machines and software, such as computers, home appliances, mobile devices, and other electronic devices, with the focus on maximizing usability and the user experience. The goal of user interface design is to make the user\'s interaction as simple and efficient as possible, in terms of accomplishing user goals (user-centered design).',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/User_interface_design'
					}
				},
				{
					id: 29,
					title: 'Agile',
					modal: {
						description: 'I\'m well-versed in the Agile methodology and I thrive in this well-structured environment. Agile software development describes a set of values and principles for software development under which requirements and solutions evolve through the collaborative effort of self-organizing cross-functional teams. It advocates adaptive planning, evolutionary development, early delivery, and continuous improvement, and it encourages rapid and flexible response to change. These principles support the definition and continuing evolution of many software development methods.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Agile_software_development'
					}
				},
				{
					id: 30,
					title: 'Animation',
					modal: {
						description: 'I love CSS Animation and I can animate anything from micro-interactions to complex SVG animations. If CSS won\'t do it, JavaScript will. CSS Animation make it possible to animate transitions from one CSS style configuration to another. Animations consist of two components, a style describing the CSS Animation and a set of keyframes that indicate the start and end states of the animation’s style, as well as possible intermediate waypoints.',
						source: '[Source]',
						sourceHref: 'https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations'
					}
				},
				{
					id: 31,
					title: 'Graphic Design',
					modal: {
						description: 'I obtained an Associate\'s degree in Graphic Design from Scottsdale Community College in 2008 Graphic design is the process of visual communication and problem-solving using one or more of typography, photography and illustration. The field is considered a subset of visual communication and communication design, but sometimes the term "Graphic design" is used synonymously.',
						source: '[Source]',
						sourceHref: 'https://en.wikipedia.org/wiki/Graphic_design'
					}
				}
			]
		}
	}
}
</script>

<style scoped lang="scss">
.skills {
	padding-top: 2rem;
	padding-bottom: 2rem;
	background-color: $accent;
	@include mq(md) {
		padding-top: 3rem;
		padding-bottom: 3rem;
	}
	@include mq(lg) {
		padding-top: 4rem;
		padding-bottom: 4rem;
	}
	&__inner {
		@include container;
	}
	&__header {
		display: flex;
		flex-direction: column;
		margin-bottom: 2rem;
		text-align: center;
	}
	&__title {
		display: block;
		width: 100%;
		margin-bottom: 0.875rem;
		color: $white;
	}
	&__description {
		margin-bottom: 0;
		font-family: $fontFamilyHeadings;
		font-weight: 300;
		&:first-of-type {
			margin-bottom: 0.5rem;
			color: $white;
			font-size: 0.875rem;
		}
		&:last-of-type {
			margin-bottom: 1rem;
			font-size: 0.75rem;
			color: darken($primary, 30%);
		}
	}

	&__items {
		position: relative;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: space-between;
		width: 100%;
	}
}
</style>