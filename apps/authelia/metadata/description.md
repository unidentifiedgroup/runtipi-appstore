**Authelia** is an open-source authentication and authorization server providing two-factor authentication and single
sign-on (SSO) for your applications via a web portal. It acts as a companion for [reverse proxies](#proxy-support) by
allowing, denying, or redirecting requests.

Documentation is available at [https://www.authelia.com/](https://www.authelia.com/).

The following is a simple diagram of the architecture:

<p align="center" style="margin:50px">
  <img src="https://www.authelia.com/images/archi.png"/>
</p>

**Authelia** can be installed as a standalone service from the [AUR](https://aur.archlinux.org/packages/authelia/),
[APT](https://apt.authelia.com/stable/debian/packages/authelia/),
[FreeBSD Ports](https://svnweb.freebsd.org/ports/head/www/authelia/), or using a
[static binary](https://github.com/authelia/authelia/releases/latest),
[.deb package]((https://github.com/authelia/authelia/releases/latest)), as a container on [Docker] or [Kubernetes].


Deployment can be orchestrated via the Helm [Chart](https://charts.authelia.com) (beta) leveraging ingress controllers
and ingress configurations.

<p align="center">
  <img src="https://www.authelia.com/images/logos/kubernetes.png" height="100"/>
  <img src="https://www.authelia.com/images/logos/docker.logo.png" width="100">
</p>

Here is what Authelia's portal looks like:

<p align="center">
  <img src="https://www.authelia.com/images/1FA.png" width="400" />
  <img src="https://www.authelia.com/images/2FA-METHODS.png" width="400" />
</p>

## Features summary

This is a list of the key features of Authelia:

* Several second factor methods:
  * **[Security Keys](https://www.authelia.com/overview/authentication/security-key/)** that support
    [FIDO2]&nbsp;[WebAuthn] with devices like a [YubiKey].
  * **[Time-based One-Time password](https://www.authelia.com/overview/authentication/one-time-password/)**
    with compatible authenticator applications.
  * **[Mobile Push Notifications](https://www.authelia.com/overview/authentication/push-notification/)**
    with [Duo](https://duo.com/).
* Password reset with identity verification using email confirmation.
* Access restriction after too many invalid authentication attempts.
* Fine-grained access control using rules which match criteria like subdomain, user, user group membership, request uri,
 request method, and network.
* Choice between one-factor and two-factor policies per-rule.
* Support of basic authentication for endpoints protected by the one-factor policy.
* Highly available using a remote database and Redis as a highly available KV store.
* Compatible with [Traefik](https://doc.traefik.io/traefik) out of the box using the
  [ForwardAuth](https://doc.traefik.io/traefik/middlewares/http/forwardauth/) middleware.
* Curated configuration from [LinuxServer](https://www.linuxserver.io/) via their
  [Swag](https://docs.linuxserver.io/general/swag) container as well as a
  [guide](https://blog.linuxserver.io/2020/08/26/setting-up-authelia/).
* Compatible with [Caddy] using the [forward_auth](https://caddyserver.com/docs/caddyfile/directives/forward_auth)
  directive.
* Kubernetes Support:
  * Compatible with several Kubernetes ingress controllers:
    * [ingress-nginx](https://www.authelia.com/integration/kubernetes/nginx-ingress/)
    * [Traefik Kubernetes CRD](https://www.authelia.com/integration/kubernetes/traefik-ingress/#ingressroute)
    * [Traefik Kubernetes Ingress](https://www.authelia.com/integration/kubernetes/traefik-ingress/#ingress)
    * [Istio](https://www.authelia.com/integration/kubernetes/istio/)
  * Beta support for installing via Helm using our [Charts](https://charts.authelia.com).
* Beta support for [OpenID Connect](https://www.authelia.com/roadmap/active/openid-connect/).

For more details take a look at the [Overview](https://www.authelia.com/overview/prologue/introduction/).

If you want to know more about the roadmap, follow [Roadmap](https://www.authelia.com/roadmap).
