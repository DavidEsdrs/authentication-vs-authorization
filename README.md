# Authentication and Authorization
## A study on the differences between authentication and authorization in REST APIs

[Authentication VS Authorization](./assets/authVSauth.png)

- Authentication means <span style="color: red">WHO</span> `IS ACCESSING SOMETHING`;
    - JWT;

- Authorization means <span style="color: red">WHAT</span> `SOMEONE CAN ACCESS`;
    - OAuth (protocol);
    - Auth0;
    - Means the SCOPE that a subject can access;
    - Access token;

### Headers
    - What is it?
        1. They come from the response of a request and have some METADATA attached by the server;
            * They can also be attached from the client side to send a request to the server;
        2. They can have session, authentication or some other kind of information that can be useful for the request or response;
    
    - There are 3 types of headers:
        1. General headers:
            - It can be either request or response related:
                - Request URL (request);
                - Request Method (request);
                - Status code (response);
                - IP;

        2. Response headers:
            * Set by the server side;
            - Content type;
            - Content length;
            - Content enconding;
            - Cache control;
            - Status code;
            - Set cookie:
                * Attaches useful cookies to the next requests made by the client side from the server side;
                * expires:
                    * Tells the browser how long stores the cookie; 

        3. Request headers:
            - Set by the client side (`cookies` can be set both client-side and server-side)
            - Accept enconding;
            - Accept language;
            - Cache control;
            - Accept:
                * Informs the server side what kind of file the client accepts (html, json, xml, image and so on)
            - Cookies:
                * Cookies set by the client side or attached by the server side using `set-cookie` header;
            - User agent:
                * What browser is requesting the data?

### Cookies
    - What is it?
        1. They are short storage set by either the client or the server side that contains useful information;
        2. Key-value pairs;
    - Why cookies?
        * Http protocol is stateless, so, cookies is a way to persist data from a request to another;
        * Can be an alternative to localStorage;