# Authentication and Authorization
## A study on the differences between authentication and authorization in REST APIs

[Authentication VS Authorization](./assets/authVSauth.png)

- Authentication means <span style="color: red">WHO</span> `IS ACCESSING SOMETHING`;
    - JWT;

- Authorization means <span style="color: red">WHAT</span> `SOMEONE CAN ACCESS`;
    - OAuth (protocol);
    - Auth0;
    - It means the SCOPE that a subject can access;
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

### Authentication

- Authetication stands for who is accessing a resource;

- Strategies used:
    * SSO: 
        It means `Single Sign-On` authentication, it is provided by trusted third-party, such as Google, Microsoft Azure, AWS, by way of token exchange to gain access to a resource ([source reference](https://stackoverflow.blog/2021/10/06/best-practices-for-authentication-and-authorization-for-rest-apis/)).
        * Advantages:
            1. It avoid the need to store user information by yourself, as it is secured by a trusted provider.
            2. Avoid implementing login and logout.
            3. User doesn't need to create a newer account, as it already takes his SSO provider account.
            4. Less data to store.


### Authorization

- Authorization stands for what can an user access or if some request for a resource is authorized;

- Strategies:
    * Role based access control (`RBAC`):
        1. Each user have one or more roles;
        2. A role manages a user's access level;
        3. Write or Read access is the easiest way to apply it;
        4. Roles is stored in the database and is related to an user;
        5. A role specifies if an user can `read`, `create` or `modify` a given resource ([source reference](https://www.gocache.com.br/dicas/o-que-e-rbac-role-based-access-control/));

    * Example:
        - In a Blog website we have the `admin`, `editor`, `author`, and `reader`.
        - A `reader` is a read-only user, he can read any post he want, but he can't edit any;
        - Each `author` can read any post he want, but can only edit his own posts;
        - A `editor` can read and edit any post he want;
        - A `admin` can edit any user role;
