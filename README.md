<img src="https://user-images.githubusercontent.com/1162160/101544140-30f02980-3973-11eb-8acd-781203261e0c.png" width="100%">

# workshop-svelte

> This workshop was designed for students enrolled in the [web developer program](https://www.yrgo.se/program/webbutvecklare/) at Yrgo.

Svelte is a modern JavaScript framework that aims to make building web applications more efficient and maintainable. Unlike traditional frameworks that rely on a runtime library, Svelte compiles your code into highly optimized JavaScript that runs directly in the browser. This approach results in faster load times, better performance, and a smaller overall code footprint.

- :books: Documentation

    - [Examples](https://svelte.dev/examples/hello-world)

    - [Tutorial](https://svelte.dev/tutorial/basics)

    - [Documentation](https://svelte.dev/docs)

    - [Learn Svelte](https://learn.svelte.dev/tutorial/welcome-to-svelte)

- :headphones: Videos

    - [Rich Harris - Rethinking reactivity](https://www.youtube.com/watch?v=AdNJ3fydeao)
    
    - [Svelte Origins: The Documentary](https://www.offerzen.com/community/svelte-origins-documentary)

## Excersises

1. Alrighty, buckle up for some hilarity! Begin your journey by moseying on over to [learn.svelte.dev](https://learn.svelte.dev/) and embarking on their side-splitting tutorial. Prepare to be edutained as the tutorial imparts the wisdom you need to effortlessly construct web applications of all shapes and sizes, boasting lightning-fast speeds and teensy-weensy footprints, all thanks to the marvel that is Svelte.

2. Before commencing with this enlightening and [engaging exercise](https://www.youtube.com/watch?v=84c7mRP7PLw), the ever-helpful teacher will provide you with a clear and comprehensive demonstration of the correct assembly process, skillfully utilizing the expansive screen at the front of the room to ensure maximum understanding and clarity for all eager participants.

    Leveraging the [kanye.rest](https://kanye.rest/) API, develop an elegant Svelte application that dynamically presents a random Kanye West quote each time the user engages with an interactive button.

    To [scaffold your first Svelte project](https://vitejs.dev/guide/), you may use the following command:

    ```bash
    npm create vite@latest kanye-rest -- --template svelte
    ```
    
    https://user-images.githubusercontent.com/499192/232570857-1dc36896-71b1-448e-a5f8-4b78fd1ef9a2.mp4

3. To provide you with an authentic and engaging development experience, we have proudly teamed up with [Mediaflow](https://mediaflow.com/) so you can utilize their API to access and retrieve data effectively. This collaboration ensures you can create practical, real-world applications by harnessing the power of Mediaflow's robust platform.

    > Mediaflow is a cloud-based  service that helps you work more efficiently with your digital assets. Collaborate, distribute, and organize easily and quickly.

    Prior to diving in, please download the resources directory and proceed to install the necessary dependencies utilizing npm. It comes pre-installed with [Tailwind CSS](https://tailwindcss.com/), you may use CSS or Tailwind, or a combination of both, to style your application. The [design isn't important](https://www.youtube.com/watch?v=dQw4w9WgXcQ), but the functionality is.
    
    ```bash
    npm install
    ```

    To proceed, obtain the Mediaflow API keys from Discord and incorporate them into the `.env.local` file, located at the root of your project.

    ```env
    VITE_MEDIAFLOW_CLIENT_ID=
    VITE_MEDIAFLOW_CLIENT_SECRET=
    VITE_MEDIAFLOW_REFRESH_TOKEN=
    ```

    If you haven't already, install the following Visual Studio Code extensions:

    - [`svelte.svelte-vscode`](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)
    - [`esbenp.prettier-vscode`](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

    List of features (complete how many you want to):

    - As a user, I can view a gallery of images fetched from Mediaflow.
    - As a user, I can click on an image to view it in a modal and see additional information.
    - As a user, I can click on the modal button to close it.
    - As a user, I can press Escape on my keyboard to close the modal.

    The API endpoints you will need to use are:

    - `https://api.mediaflow.com/1/oauth2/token` - to fetch an access token
    - `https://api.mediaflow.com/1/file/latest` - to fetch a list of images
    - `https://api.mediaflow.com/1/file/{{id}}` - to fetch a single image

    [Please see the documentation for more information.](https://documenter.getpostman.com/view/23189985/2s8YzL4meR)

    Should you find this a tad overwhelming, fear not! You can always refer to the solutions for guidance and inspiration. For instance, take a look at [this solution](solutions/mediaflow/src/lib/api.js) demonstrating how to perform GET requests to retrieve data from Mediaflow.

    https://user-images.githubusercontent.com/499192/232570273-e076ef4d-040c-4729-a437-452ecd5959ca.mp4
    
    Keep in mind, prior to delving into the realm of Svelte, it's essential to embrace the enduring wisdom passed down to [developers](https://www.youtube.com/watch?v=Vhh_GeBPOhs) at Ericsson: **"Work harder, not smarter!"**
