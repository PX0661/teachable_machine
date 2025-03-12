# Teachable Machine Community

![Teachable Machine](./teachablemachine.gif)

### What is Teachable Machine?

[Teachable Machine](https://teachablemachine.withgoogle.com/) is a web-based tool that makes creating machine learning models fast, easy, and accessible for everyone. [You can try it here](https://teachablemachine.withgoogle.com/).

### Who is it for?

Educators, artists, students, innovators, makers of all kinds – really, anyone who has an idea they want to explore. No prerequisite machine learning knowledge required.

### How does it work?

You train a computer to recognize your images, sounds, and poses without writing any machine learning code. Then, use your model in your own projects, sites, apps, and more.

### What is this repository for?

This repository contains two components of [Teachable Machine](https://teachablemachine.withgoogle.com/):

1. **A [libraries](/libraries) section** that contains all of the machine learning code used in Teachable Machine. Under the hood we use [Tensorflow.js](https://www.tensorflow.org/js), a library for machine learning in Javascript, to train and run the models you make in your web browser. The `libraries` section also contains the API for [image](/libraries/image), [audio](/libraries/audio), and [pose](/libraries/pose) helper libraries that make it easier to use the models exported by Teachable Machine in your own projects.

2. **A [snippets](/snippets) section** that contains markdown snippets that are being displayed inside the export panel in [Teachable Machine](https://teachablemachine.withgoogle.com/). These snippets contain code and instructions on how to use the exported models from Teachable Machine in languages like Javascript, Java and Python.

### How can I send feedback or get in contact with you?

You have a few options:

- Share your projects using [#teachablemachine](https://twitter.com/hashtag/teachablemachine) on Twitter or on the [Experiments with Google](https://experiments.withgoogle.com/submit) page.
- Open an issue in this repository.

## Community Contributions and Projects

- [Teachable Machine Node Library for image models](https://github.com/tr7zw/teachablemachine-node-example) (Archived and now continued [here](https://github.com/drinkspiller/teachablemachine-node-example/))
- [Teachable Machine Mobile for image models](https://github.com/mstale007/Teachable_Machine_Mobile/tree/master)

## How to Run

This repository contains libraries and code snippets for Teachable Machine. Here's how to use them:

### Libraries

The libraries can be used in two ways:

#### 1. Via Script Tag

**Image Library:**
```html
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest/dist/tf.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@teachablemachine/image@latest/dist/teachablemachine-image.min.js"></script>
```

**Pose Library:**
```html
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest/dist/tf.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@teachablemachine/pose@latest/dist/teachablemachine-pose.min.js"></script>
```

**Audio Library:**
```html
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest/dist/tf.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/speech-commands@latest/dist/speech-commands.min.js"></script>
```

#### 2. Via NPM

**Image Library:**
```bash
npm i @tensorflow/tfjs
npm i @teachablemachine/image
```

**Pose Library:**
```bash
npm i @tensorflow/tfjs
npm i @teachablemachine/pose
```

**Audio Library:**
```bash
npm i @tensorflow/tfjs
npm i @tensorflow-models/speech-commands
```

### Development

To develop or modify the libraries:

1. Clone the repository:
   ```bash
   git clone https://github.com/PX0661/teachable_machine.git
   cd teachable_machine
   ```

2. Install dependencies and build the library you want to work on:
   ```bash
   # For image library
   cd libraries/image
   npm install
   npm run build
   
   # For pose library
   cd libraries/pose
   npm install
   npm run build
   ```

3. Run tests:
   ```bash
   npm test
   ```

4. For development with live reloading:
   ```bash
   npm run dev
   ```

### Using Docker

This repository includes Docker configurations for development and running the converter services.

#### Development Environment

To use Docker for development:

1. Build the Docker image for the libraries:
   ```bash
   cd libraries
   docker build -t teachablemachine-libraries .
   ```

2. Run the Docker container:
   ```bash
   docker run -it --rm -v $(pwd):/app teachablemachine-libraries run build
   ```

#### Converter Services

The repository includes Docker configurations for running the converter services:

1. Navigate to the converter directory:
   ```bash
   cd snippets/converter
   ```

2. Build and run the converter services using Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. The services will be available at:
   - Tiny Converter: http://localhost:9001
   - Image Converter: http://localhost:9002
   - Audio Converter: http://localhost:9003

4. To stop the services:
   ```bash
   docker-compose down
   ```

### Snippets

To serve the code snippets locally:

1. Navigate to the snippets directory:
   ```bash
   cd snippets
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the HTTP server:
   ```bash
   npm start
   ```

4. The snippets will be available at `http://localhost:8080`

### Using the Models

For detailed examples of how to use the models, refer to the individual library READMEs:
- [Image Library](/libraries/image/)
- [Pose Library](/libraries/pose/)
- [Audio Library](/libraries/audio/)

Or check the code snippets in the [snippets](/snippets/) directory.

## Disclaimer

This is an experiment, not an official Google product. We’ll do our best to support and maintain this experiment but your mileage may vary.

We encourage open sourcing projects as a way of learning from each other. Please respect our and other creators’ rights, including copyright and trademark rights when present, when sharing these works and creating derivative work. If you want more info on Google's policy, you can find that [here](https://www.google.com/permissions/).
