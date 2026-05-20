# Knot Pro

<div align="center">

[![release](https://img.shields.io/github/v/release/paularlott/knot-pro)](https://github.com/paularlott/knot-pro/releases/latest)
[![License](https://img.shields.io/badge/License-EULA-blue.svg)](LICENSE.txt)

</div>

Knot Pro is the commercial version of [Knot](https://github.com/paularlott/knot), a powerful tool to manage Cloud Development Environments within a Nomad cluster or local environments. It provides a seamless blend of a user-friendly web interface and a command line interface. This dual approach streamlines the deployment process and simplifies access to development environments, making management an effortless endeavor and eliminating the need for each developer to manage their own configurations.

Knot Pro builds on the Apache 2.0 licensed Knot Core project, but the Pro-only
features in this repository are closed-source, licensed under the
[Knot Pro EULA](LICENSE.txt), and protected by licence-key validation.

## Features

- **OAuth Authentication:** GitHub and Google OAuth for seamless single sign-on.
- **External Secret Providers:** Resolve template secrets from Vault with configurable caching.
- **Visual Port Forwarding:** Pro-only visual management of port forwarding between spaces from the Spaces page, including persistent forwards for stopped spaces.
- **User Activity Controls:** Pro-only controls let you disable filesystem-based user activity collection globally or per template to reduce watcher overhead when you do not need activity summaries.
- **Web-Based Management Interface:** Provides an easy-to-use, browser-based interface for managing environments.
- **Visual Studio Code Integration:** Allows access to Visual Studio Code right from your browser.
- **Code Server Integration:** Offers access to Code Server right from your browser.
- **Terminal Access:** Offers in-browser terminal access for seamless command-line operations.
- **Command-Line Tools:** Simplifies container access with handy command-line tools.
- **User & Permission Management:** Effectively manage users and their permissions.
- **Groups:** Control which templates are available to users.
- **Environment Templates:** Customizable templates for creating consistent development environments.
- **Integration with Nomad:** Ensures seamless integration with Nomad for efficient cluster management.
- **Local Containers:** Run containers on the local machine using Docker or Podman.
- **Quotas:** Limit by resource usage and by number of spaces per user.
- **Development URL Management:** Automatically generated URLs for development spaces.
- **Support for VNC:** Support for web based VNC servers such as KasmVNC.
- **Remote Servers** Maximize performance by deploying environment close to developers but manage templates and users from anywhere, no single point failure.
- **Custom Roles:** Create custom roles to manage permissions.
- **Sharing:** Spaces can be shared with multiple users, with a shared `shares` API shape that supports collaborative access across the web UI, API clients, and scripting wrappers.
- **Logging:** Syslog compatible interface allows logging and display within a window.
- **Tunneling:** Securely expose development environments to the internet when required.
- **Local Services** Securely connect to services on your local machine from within a space.
- **API:** Provides an API for integration with other systems.

## API Versioning

The API version is specified in the request header:

```http
X-Knot-Api-Version: 2025-03-10
```

Any non-breaking changes are available in all versions of the API while breaking changes are only available in the latest version of the API.

## Security

knot is designed to be used within trusted environments rather than on the open internet, that is it is expected to be run on a private network with developers connecting to the it via a VPN or similar technology.

For complex deployments over many different locations a mesh network may be appropriate.

When tunneling is enabled the tunnel port is separate from the web interface and the agent interface, it is expected that public traffic be directed to the tunnel interface only.

Time-based one-time passwords (TOTP) should be enabled if the web interface is exposed to the internet. The TOTP code works with Google Authenticator, Microsoft Authenticator, and other TOTP apps.

## Documentation

Documentation and [Getting Started](https://getknot.dev/docs/getting-started/).

## Licensing

- **Knot Core** is open source and distributed separately under the Apache License 2.0.
- **Knot Pro** in this repository is a commercial distribution under the [Knot Pro EULA](LICENSE.txt).
- Pro-only features are closed-source and require a valid licence key to activate.
- Third-party dependency licences are listed in [THIRD_PARTY_LICENSES.txt](THIRD_PARTY_LICENSES.txt).

## User Activity Collection

- Set `server.disable_user_activity = true` to disable filesystem-based user activity collection for every space on the server.
- In Pro, each template can disable user activity collection individually from the template form.
- The setting takes effect the next time a space from the template starts or reconnects.

## Icons

Icons are sourced from:

- https://heroicons.com/outline
- https://flowbite.com/icons/
- https://github.com/homarr-labs/dashboard-icons
- https://github.com/devicons/devicon

### Legal

**Disclaimer**: All product names, trademarks, and registered trademarks are the property of their respective owners. Icons are used for identification purposes only and do not imply endorsement.
