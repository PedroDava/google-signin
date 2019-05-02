# google-signin

google-sign upgraded from polymer 2.0 to polymer 3.0.


```
import '@google-web-components/google-signin/google-signin.js';
import '@google-web-components/google-signin/google-signin-aware.js';


class MyView extends PolymerElement {
  static get template() {
    return html`
<style include="shared-styles">
:host {
display: block;

padding: 10px;
}
</style>



<google-signin client-id="XXXXXX.apps.googleusercontent.com" scopes="https://www.googleapis.com/auth/userinfo.email" label-signin="Sign-in" on-google-signin-success="_loginSuccess"></google-signin>


<google-signing-aware is-authorized = "{{_authorized}}"></google-signing-aware>


`;
  }

  static get properties() {
    return {
      _authorized: {
        reflectToAttribute: true,
        notify:true,
      }
    };
  }

  _loginSuccess(){
    if(this._authorized)
      console.log( "Hello Google world");
  }
}


window.customElements.define('my-view7', MyView7);
