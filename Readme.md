# DiscordChatExporter

[![Status](https://img.shields.io/badge/status-maintenance-ffd700.svg)](https://github.com/Tyrrrz/.github/blob/prime/docs/project-status.md)
[![Made in Ukraine](https://img.shields.io/badge/made_in-ukraine-ffd700.svg?labelColor=0057b7)](https://tyrrrz.me/ukraine)
[![Build](https://img.shields.io/github/actions/workflow/status/Tyrrrz/DiscordChatExporter/main.yml?branch=prime)](https://github.com/Tyrrrz/DiscordChatExporter/actions)
[![Coverage](https://img.shields.io/codecov/c/github/Tyrrrz/DiscordChatExporter/prime)](https://codecov.io/gh/Tyrrrz/DiscordChatExporter)
[![Release](https://img.shields.io/github/release/Tyrrrz/DiscordChatExporter.svg)](https://github.com/Tyrrrz/DiscordChatExporter/releases)
[![Downloads](https://img.shields.io/github/downloads/Tyrrrz/DiscordChatExporter/total.svg)](https://github.com/Tyrrrz/DiscordChatExporter/releases)
[![Pulls](https://img.shields.io/docker/pulls/tyrrrz/discordchatexporter)](https://hub.docker.com/r/tyrrrz/discordchatexporter)
[![Discord](https://img.shields.io/discord/869237470565392384?label=discord)](https://discord.gg/2SUWKFnHSm)
[![Fuck Russia](https://img.shields.io/badge/fuck-russia-e4181c.svg?labelColor=000000)](https://twitter.com/tyrrrz/status/1495972128977571848)

<table>
    <tr>
        <td width="99999" align="center">Development of this project is entirely funded by the community. <b><a href="https://tyrrrz.me/donate">Consider donating to support!</a></b></td>
    </tr>
</table>

<p align="center">
    <img src="favicon.png" alt="Icon" />
</p>

**DiscordChatExporter** is an application that can be used to export message history from any [Discord](https://discord.com) channel to a file.
It works with direct messages, group messages, and server channels, and supports Discord's dialect of markdown as well as most other rich media features.

> [!WARNING]
> While **DiscordChatExporter** allows it, automating user accounts is against Discord TOS and may result in you getting banned.
> If possible, use a bot to export chat logs from accessible channels.

## Terms of use<sup>[[?]](https://github.com/Tyrrrz/.github/blob/prime/docs/why-so-political.md)</sup>

By using this project or its source code, for any purpose and in any shape or form, you grant your **implicit agreement** to all the following statements:

- You **condemn Russia and its military aggression against Ukraine**
- You **recognize that Russia is an occupant that unlawfully invaded a sovereign state**
- You **support Ukraine's territorial integrity, including its claims over temporarily occupied territories of Crimea and Donbas**
- You **reject false narratives perpetuated by Russian state propaganda**

To learn more about the war and how you can help, [click here](https://tyrrrz.me/ukraine). Glory to Ukraine! 🇺🇦

## Download

- **Graphical user interface** (desktop app):
  - 🟢 **[Stable release](https://github.com/Tyrrrz/DiscordChatExporter/releases/latest)**: look for `DiscordChatExporter.*.zip`
  - 🟠 [CI build](https://github.com/Tyrrrz/DiscordChatExporter/actions/workflows/main.yml): look for `DiscordChatExporter.*.zip`
  - 📦 [Scoop](https://scoop.sh/#/apps?q=DiscordChatExporter&p=1&id=c71b7367623c560a2dc746b9739b9568b79b59ae): `scoop install extras/discordchatexporter` (community-maintained)
  - 📦 [WinGet](https://winstall.app/apps/Tyrrrz.DiscordChatExporter.GUI): `winget install Tyrrrz.DiscordChatExporter.GUI` (community-maintained)
  - 📦 [AUR](https://aur.archlinux.org/packages/discord-chat-exporter-gui): `yay -S discord-chat-exporter-gui` (community-maintained)
  - 📦 [Nix](https://search.nixos.org/packages?show=discordchatexporter-desktop): `nix-shell -p discordchatexporter-desktop` (community-maintained)
- **Command-line interface** (terminal app):
  - 🟢 **[Stable release](https://github.com/Tyrrrz/DiscordChatExporter/releases/latest)**: look for `DiscordChatExporter.Cli.*.zip`
  - 🟠 [CI build](https://github.com/Tyrrrz/DiscordChatExporter/actions/workflows/main.yml): look for `DiscordChatExporter.Cli.*.zip`
  - 🐋 [Docker](https://hub.docker.com/r/tyrrrz/discordchatexporter): `docker pull tyrrrz/discordchatexporter`
  - 📦 [WinGet](https://winstall.app/apps/Tyrrrz.DiscordChatExporter.CLI): `winget install Tyrrrz.DiscordChatExporter.CLI` (community-maintained)
  - 📦 [AUR](https://aur.archlinux.org/packages/discord-chat-exporter-cli): `yay -S discord-chat-exporter-cli` (community-maintained)
  - 📦 [Nix](https://search.nixos.org/packages?show=discordchatexporter-cli): `nix-shell -p discordchatexporter-cli` (community-maintained)
Pull request overview
Adds two Agent Skills documents under the canonical skills/ publishing location so this repo can be used as a gh skill install source.

Changes:
		Git installation

Normally you can just do "make" followed by "make install", and that
will install the git programs in your own ~/bin/ directory.  If you want
to do a global install, you can do

	$ make prefix=/usr all doc info ;# as yourself
	# make prefix=/usr install install-doc install-html install-info ;# as root

(or prefix=/usr/local, of course).  Just like any program suite
that uses $prefix, the built results have some paths encoded,
which are derived from $prefix, so "make all; make prefix=/usr
install" would not work.

The beginning of the Makefile documents many variables that affect the way
git is built.  You can override them either from the command line, or in a
config.mak file.

Alternatively you can use autoconf generated ./configure script to
set up install paths (via config.mak.autogen), so you can write instead

	$ make configure ;# as yourself
	$ ./configure --prefix=/usr ;# as yourself
	$ make all doc ;# as yourself
	# make install install-doc install-html;# as root

If you're willing to trade off (much) longer build time for a later
faster git you can also do a profile feedback build with

	$ make prefix=/usr profile
	# make prefix=/usr PROFILE=BUILD install

This will run the complete test suite as training workload and then
rebuild git with the generated profile feedback. This results in a git
which is a few percent faster on CPU intensive workloads.  This
may be a good tradeoff for distribution packagers.

Alternatively you can run profile feedback only with the git benchmark
suite. This runs significantly faster than the full test suite, but
has less coverage:

	$ make prefix=/usr profile-fast
	# make prefix=/usr PROFILE=BUILD install

Or if you just want to install a profile-optimized version of git into
your home directory, you could run:

	$ make profile-install

or
	$ make profile-fast-install

As a caveat: a profile-optimized build takes a *lot* longer since the
git tree must be built twice, and in order for the profiling
measurements to work properly, ccache must be disabled and the test
suite has to be run using only a single CPU.  In addition, the profile
feedback build stage currently generates a lot of additional compiler
warnings.

Issues of note:

 - Ancient versions of GNU Interactive Tools (pre-4.9.2) installed a
   program "git", whose name conflicts with this program.  But with
   version 4.9.2, after long hiatus without active maintenance (since
   around 1997), it changed its name to gnuit and the name conflict is no
   longer a problem.

   NOTE: When compiled with backward compatibility option, the GNU
   Interactive Tools package still can install "git", but you can build it
   with --disable-transition option to avoid this.

 - You can use git after building but without installing if you want
   to test drive it.  Simply run git found in bin-wrappers directory
   in the build directory, or prepend that directory to your $PATH.
   This however is less efficient than running an installed git, as
   you always need an extra fork+exec to run any git subcommand.

   It is still possible to use git without installing by setting a few
   environment variables, which was the way this was done
   traditionally.  But using git found in bin-wrappers directory in
   the build directory is far simpler.  As a historical reference, the
   old way went like this:

	GIT_EXEC_PATH=`pwd`
	PATH=`pwd`:$PATH
	GITPERLLIB=`pwd`/perl/build/lib
	export GIT_EXEC_PATH PATH GITPERLLIB

 - By default (unless NO_PERL is provided) Git will ship various perl
   scripts. However, for simplicity it doesn't use the
   ExtUtils::MakeMaker toolchain to decide where to place the perl
   libraries. Depending on the system this can result in the perl
   libraries not being where you'd like them if they're expected to be
   used by things other than Git itself.

   Manually supplying a perllibdir prefix should fix this, if this is
   a problem you care about, e.g.:

       prefix=/usr perllibdir=/usr/$(/usr/bin/perl -MConfig -wle 'print substr $Config{installsitelib}, 1 + length $Config{siteprefixexp}')

   Will result in e.g. perllibdir=/usr/share/perl/5.26.1 on Debian,
   perllibdir=/usr/share/perl5 (which we'd use by default) on CentOS.

 - Unless NO_PERL is provided Git will ship various perl libraries it
   needs. Distributors of Git will usually want to set
   NO_PERL_CPAN_FALLBACKS if NO_PERL is not provided to use their own
   copies of the CPAN modules Git needs.

 - Git is reasonably self-sufficient, but does depend on a few external
   programs and libraries.  Git can be used without most of them by adding
   the appropriate "NO_<LIBRARY>=YesPlease" to the make command line or
   config.mak file.

	- "zlib", the compression library. Git won't build without it.

	- "ssh" is used to push and pull over the net.

	- A POSIX-compliant shell is required to run some scripts needed
	  for everyday use (e.g. "bisect", "request-pull").

	- "Perl" version 5.26.0 or later is needed to use some of the
	  features (e.g. sending patches using "git send-email",
	  interacting with svn repositories with "git svn").  If you can
	  live without these, use NO_PERL.  Note that recent releases of
	  Redhat/Fedora are reported to ship Perl binary package with some
	  core modules stripped away (see https://lwn.net/Articles/477234/),
	  so you might need to install additional packages other than Perl
	  itself, e.g. Digest::MD5, File::Spec, File::Temp, Net::Domain,
	  Net::SMTP, and Time::HiRes.

	- "libcurl" library is used for fetching and pushing
	  repositories over http:// or https://, as well as by
	  git-imap-send. If you do not need that functionality,
	  use NO_CURL to build without it.

	  Git requires version "7.61.0" or later of "libcurl" to build
	  without NO_CURL. This version requirement may be bumped in
	  the future.

	- "expat" library; git-http-push uses it for remote lock
	  management over DAV.  Similar to "curl" above, this is optional
	  (with NO_EXPAT).

	- "wish", the Tcl/Tk windowing shell is used in gitk to show the
	  history graphically, and in git-gui.  If you don't want gitk or
	  git-gui, you can use NO_TCLTK.

	- A gettext library is used by default for localizing Git. The
	  primary target is GNU libintl, but the Solaris gettext
	  implementation also works.

	  We need a gettext.h on the system for C code, gettext.sh (or
	  Solaris gettext(1)) for shell scripts, and libintl-perl for Perl
	  programs.

	  Set NO_GETTEXT to disable localization support and make Git only
	  use English. Under autoconf the configure script will do this
	  automatically if it can't find libintl on the system.

	- Python version 2.7 or later is needed to use the git-p4 interface
	  to Perforce.

 - Some platform specific issues are dealt with Makefile rules,
   but depending on your specific installation, you may not
   have all the libraries/tools needed, or you may have
   necessary libraries at unusual locations.  Please look at the
   top of the Makefile to see what can be adjusted for your needs.
   You can place local settings in config.mak and the Makefile
   will include them.  Note that config.mak is not distributed;
   the name is reserved for local settings.

 - To build and install documentation suite, you need to have
   the asciidoc/xmlto toolchain.  Because not many people are
   inclined to install the tools, the default build target
   ("make all") does _not_ build them.

   "make doc" builds documentation in man and html formats; there are
   also "make man", "make html" and "make info". Note that "make html"
   requires asciidoc, but not xmlto. "make man" (and thus make doc)
   requires both.

   "make install-doc" installs documentation in man format only; there
   are also "make install-man", "make install-html" and "make
   install-info".

   Building and installing the info file additionally requires
   makeinfo and docbook2X.  Version 0.8.3 is known to work.

   Building and installing the pdf file additionally requires
   dblatex.  Version >= 0.2.7 is known to work.

   All formats require at least asciidoc 8.4.1. Alternatively, you can
   use Asciidoctor (requires Ruby) by passing USE_ASCIIDOCTOR=YesPlease
   to make. You need at least Asciidoctor version 1.5.

   There are also "make quick-install-doc", "make quick-install-man"
   and "make quick-install-html" which install preformatted man pages
   and html documentation. To use these build targets, you need to
   clone two separate git-htmldocs and git-manpages repositories next
   to the clone of git itself.

   The minimum supported version of docbook-xsl is 1.74.

   Users attempting to build the documentation on Cygwin may need to ensure
   that the /etc/xml/catalog file looks something like this:

   <?xml version="1.0"?>
   <!DOCTYPE catalog PUBLIC
      "-//OASIS//DTD Entity Resolution XML Catalog V1.0//EN"
      "http://www.oasis-open.org/committees/entity/release/1.0/catalog.dtd"
   >
   <catalog xmlns="urn:oasis:names:tc:entity:xmlns:xml:catalog">
     <rewriteURI
       uriStartString = "http://docbook.sourceforge.net/release/xsl/current"
       rewritePrefix = "/usr/share/sgml/docbook/xsl-stylesheets"
     />
     <rewriteURI
       uriStartString="http://www.oasis-open.org/docbook/xml/4.5"
       rewritePrefix="/usr/share/sgml/docbook/xml-dtd-4.5"
     />
  </catalog>

  This can be achieved with the following two xmlcatalog commands:

  xmlcatalog --noout \
     --add rewriteURI \
        http://docbook.sourceforge.net/release/xsl/current \
        /usr/share/sgml/docbook/xsl-stylesheets \
     /etc/xml/catalog

  xmlcatalog --noout \
     --add rewriteURI \
         http://www.oasis-open.org/docbook/xml/4.5/xsl/current \
         /usr/share/sgml/docbook/xml-dtd-4.5 \
     /etc/xml/catalog

Add skills/gh/SKILL.md with agent-focused guidance for reliable gh CLI usage (JSON output, pagination, repo targeting, gh api fallback).
Add skills/gh-skill/SKILL.md describing how agents can discover/preview/install/update/publish skills via gh skill.
Show a summary per file
File	Description
skills/gh/SKILL.md	New skill doc capturing operational “gotchas” and patterns for using gh from agents.
skills/gh-skill/SKILL.md	New skill doc for self-managing skills via gh skill workflows and publishing conventions.
> [!IMPORTANT]
> To launch the GUI version of the app on MacOS, you may need to first remove the downloaded file from quarantine.
> You can do that by running the following command in the terminal: `xattr -rd com.apple.quarantine DiscordChatExporter.app`.

> [!NOTE]
> Community-maintained packages are published independently from this repository and may not always be up to date with the latest release.

> [!NOTE]
> If you're unsure which build is right for your system, consult with [this page](https://useragent.cc) to determine your OS and CPU architecture.

## Features

- Cross-platform graphical and command-line interfaces
- Authentication via either a user or a bot token
- Multiple output formats: HTML (dark/light), TXT, CSV, JSON
- Support for markdown, attachments, embeds, emoji, and other rich media features
- File partitioning, date ranges, message filtering, and other export options
- Self-contained exports that can be viewed offline

## Screenshots

![channel list](.assets/list.png)
![rendered output](.assets/output.png)

## See also

- [**Chat Analytics**](https://github.com/mlomb/chat-analytics) — solution for analyzing chat patterns of Discord users, using exports produced by **DiscordChatExporter**.
- [**DiscordChatExporter-frontend**](https://github.com/slatinsky/DiscordChatExporter-frontend) — convenient viewer for exports produced by **DiscordChatExporter**.
AGENCIA DE MARKETING ORIENTADA A RESULTADOS.
Escalamos la facturación mensual de tu negocio entre 50.000€ a +100.000€. Garantizado por contrato. .
Implementamos un sistema con IA que encuentra a tu cliente ideal y te entrega citas cualificadas y listas para cerrar directamente en tu agenda. Si no alcanzamos el objetivo de ingresos no pagas.
TypeScript               75 repos            ██████████████░░░░░░░░░░░   57.25 % 
HTML                     4 repos             █░░░░░░░░░░░░░░░░░░░░░░░░   03.05 % 
Shell                    3 repos             █░░░░░░░░░░░░░░░░░░░░░░░░   02.29 % 
SCSS                     2 repos             ░░░░░░░░░░░░░░░░░░░░░░░░░   01.53 % 
Rich Text Format         1 repo              ░░░░░░░░░░░░░░░░░░░░░░░░░   00.76 % fuzzy-names-ts/
├── src/
│   ├── index.ts                 # Main export
│   ├── types/
│   │   ├── config.ts            # Configuration types
│   │   ├── results.ts           # Result types
│   │   ├── algorithms.ts        # Algorithm interfaces
│   │   └── options.ts           # Option types
│   │
│   ├── core/
│   │   ├── FuzzyNamesSearch.ts  # Main class
│   │   ├── IndexEngine.ts       # Indexing
│   │   ├── ScoringEngine.ts     # Scoring logic
│   │   └── FilterEngine.ts      # Filtering
│   │
│   ├── algorithms/
│   │   ├── levenshtein/
│   │   │   ├── standard.ts
│   │   │   ├── damerau.ts
│   │   │   └── optimized.ts
│   │   ├── phonetic/
│   │   │   ├── base.ts
│   │   │   ├── hindi.ts
│   │   │   ├── marathi.ts
│   │   │   ├── tamil.ts
│   │   │   ├── english.ts
│   │   │   └── index.ts
│   │   ├── jaro/
│   │   │   └── jaro-winkler.ts
│   │   ├── combined.ts          # Hybrid scoring
│   │   └── custom.ts            # Custom algorithm support
│   │
│   ├── utils/
│   │   ├── string.ts            # String utilities
│   │   ├── type-guards.ts       # Type checking
│   │   ├── extractors.ts        # Data extraction
│   │   ├── normalization.ts     # Text normalization
│   │   ├── validation.ts        # Config validation
│   │   ├── performance.ts       # Profiling
│   │   └── cache.ts             # LRU cache
│   │
│   ├── presets/
│   │   ├── strict-phonetic.ts
│   │   ├── balanced.ts
│   │   ├── lenient.ts
│   │   └── index.ts
│   │
│   └── plugins/
│       ├── analytics.ts
│       ├── logging.ts
│       └── memory-monitor.ts
│
├── tests/
│   ├── unit/
│   │   ├── algorithms/
│   │   ├── core/
│   │   └── utils/
│   ├── integration/
│   │   ├── search-workflows.test.ts
│   │   ├── data-types.test.ts
│   │   └── performance.test.ts
│   ├── fixtures/
│   │   ├── indian-names.json
│   │   ├── test-data.ts
│   │   └── benchmark-data.ts
│   └── setup.ts
│
├── examples/
│   ├── basic-search.ts
│   ├── nested-objects.ts
│   ├── split-names.ts
│   ├── custom-scorer.ts
│   ├── batch-operations.ts
│   └── browser-usage.html
│
├── bench/
│   ├── algorithms.bench.ts
│   ├── full-search.bench.ts
│   └── memory.bench.ts
│
├── docs/
│   ├── api.md
│   ├── guide.md
│   ├── phonetic-system.md
│   ├── performance.md
│   └── migration.md
│
├── build/
│   ├── tsconfig.json
│   ├── tsconfig.esm.json
│   ├── esbuild.config.js
│   └── rollup.config.js
│
├── .github/
│   └── workflows/
│       ├── test.yml
│       ├── coverage.yml
│       └── publish.yml
│
├── package.json
├── README.md
├── CHANGELOG.md
└── LICENSE// Test pyramid
//        △
//       / \
//      /   \
//     /  E2E \         (Search workflows, real data)
//    /       \
//   /---------\
//  /           \
// / Integration \    (Algorithm combinations, data formats)
// /             \
// /_____________\
// /             /
// / Unit Tests / (Individual algorithms, utilities)
// /___________/

// Coverage targets
- Unit: 95%+
- Integration: 85%+
- Overall: 90%+https://github.com/K11MCH1/AdrenoToolsDrivers# ¿Qué son GitHub Codespaces?

Más información sobre GitHub Codespaces.

## Presentación

Un codespace es un ambiente de desarrollo que se hospeda en la nube. Puedes personalizar tu proyecto para GitHub Codespaces confirmando los archivos de configuración en el repositorio (lo que se conoce a menudo como configuración como código). Esta acción crea una configuración de codespace repetible para todos los usuarios del proyecto. Consulta [Introducción a los contenedores dev](/es/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers).

Cada codespace que creas se hospeda en GitHub en un contenedor Docker, el cual se ejecuta en una máquina virtual. Puedes elegir entre una selección de tipos de máquina virtual que tienen desde 2 núcleos, 8 GB de RAM y 32 GB de almacenamiento hasta 32 núcleos, 128 GB de RAM y 128 GB de almacenamiento.

De forma predeterminada, el entorno de desarrollo de los codespaces se crea a partir de una imagen de Ubuntu Linux que incluye una selección de lenguajes y herramientas populares, pero puedes usar una imagen basada en cualquier distribución de Linux y configurarla según tus requisitos específicos. Independientemente de tu sistema operativo local, el codespace se ejecutará en un entorno de Linux. Windows y macOS no son sistemas operativos compatibles con el contenedor de desarrollo remoto.

Puede conectarte a sus codespaces desde el explorador, desde Visual Studio Code o mediante GitHub CLI. Al conectarte, accedes directamente al contenedor Docker. Solo tiene acceso limitado al host de máquina virtual de Linux externo.

![Diagrama que muestra la relación entre un editor de código y un espacio de código que se ejecuta en una máquina virtual Azure.](/assets/images/help/codespaces/codespaces-diagram.png)

## Uso de GitHub Codespaces

Para comenzar a desarrollar utilizando recursos de cómputo basados en la nube, puedes crear un codespace desde una plantilla o cualquier rama o confirmación en un repositorio. Al crear un espacio de código a partir de una plantilla, puede empezar desde una plantilla en blanco o elegir una plantilla adecuada para el trabajo que está realizando.

Para empezar a trabajar con GitHub Codespaces, consulta [Inicio rápido para GitHub Codespaces](/es/codespaces/quickstart). Para más información sobre cómo crear un codespace, consulta [Creación de un codespace para un repositorio](/es/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository) o [Creación de un codespace a partir de una plantilla](/es/codespaces/developing-in-codespaces/creating-a-codespace-from-a-template). Si quieres volver a un codespace que ya has creado, consulta [Apertura de un codespace existente](/es/codespaces/developing-in-codespaces/opening-an-existing-codespace). Para más información sobre cómo funciona GitHub Codespaces, consulta [Análisis en profundidad de GitHub Codespaces](/es/codespaces/about-codespaces/deep-dive).

### Uso de codespaces propiedad de tu cuenta personal

Todas las cuentas personales de GitHub tienen una cuota mensual de uso gratuito de GitHub Codespaces incluida en el plan Gratis o Pro. Puedes empezar a usar GitHub Codespaces en tu cuenta personal sin cambiar ninguna configuración ni proporcionar detalles de pago.

Si creas un codespace desde un repositorio propiedad de la organización, el uso del codespace se cobrará a la organización (si la organización está configurada para ello) o a tu cuenta personal.

Para seguir usando GitHub Codespaces más allá del almacenamiento y del uso de proceso mensuales incluidos, proporciona la información de pago y establece un límite de gasto. Consulta [facturación de GitHub Codespaces](/es/billing/managing-billing-for-your-products/managing-billing-for-github-codespaces/about-billing-for-github-codespaces).

### Uso de codespaces propiedad de la organización

Los propietarios de las organizaciones que tengan planes de GitHub Team y GitHub Enterprise pueden pagar el uso que sus miembros y colaboradores hagan de GitHub Codespaces. Esto se aplica a codespaces creados a partir de repositorios propiedad de la organización. Consulta [Selección de quién posee y paga los codespaces de una organización](/es/codespaces/managing-codespaces-for-your-organization/choosing-who-owns-and-pays-for-codespaces-in-your-organization). Puedes establecer un límite de gasto para el uso de GitHub Codespaces en tu organización o cuenta empresarial. Consulta [Configuración de presupuestos para controlar el gasto en productos medidos](/es/billing/managing-billing-for-your-products/managing-billing-for-github-codespaces/managing-the-spending-limit-for-github-codespaces).

Si el uso de un codespace va a facturarse a una organización o empresa, se muestra cuando se crea el codespace. Consulta [Creación de un codespace para un repositorio](/es/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository#creating-a-codespace-for-a-repository). Los codespaces que se facturan a una organización, o a su empresa matriz, son propiedad de la organización y pueden ser eliminados por un propietario de esta. Consulta [Borrar un codespace](/es/codespaces/developing-in-a-codespace/deleting-a-codespace#deleting-codespaces-in-your-organization).

La capacidad de crear codespaces a partir de repositorios que posea la organización depende de varios factores, como la visibilidad del repositorio y la configuración de la organización o su empresa principal. Para más información, consulta [Solucionar problemas de creación y borrado de codespaces](/es/codespaces/troubleshooting/troubleshooting-creation-and-deletion-of-codespaces#no-access-to-create-a-codespace).

### Personalización de GitHub Codespaces

Para personalizar los runtimes y las herramientas del codespace, puedes crear una o varias configuraciones de contenedor de desarrollo para el repositorio. Agregar configuraciones de contenedor de desarrollo al repositorio permite definir una elección de diferentes entornos de desarrollo que sean adecuados para el trabajo que harán las personas en el repositorio.

Si crea un codespace desde un repositorio sin configuraciones de contenedor de desarrollador, GitHub Codespaces clonará el repositorio en un entorno con la imagen de contenedor de desarrollador predeterminada que incluye muchas herramientas, lenguajes y entornos en tiempo de ejecución. Si creas un codespace a partir de una plantilla, puedes empezar con alguna configuración inicial sobre la imagen predeterminada. Consulta [Introducción a los contenedores dev](/es/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers).

Puedes personalizar aspectos del entorno de codespace mediante un repositorio de [dotfiles](https://dotfiles.github.io/tutorials/) público. Puedes usar dotfiles para establecer alias y preferencias de shell, o para instalar tus preferencias personales de las herramientas que quieras usar. Si usas GitHub Codespaces en el explorador o en Visual Studio Code, puedes usar [Settings Sync](https://code.visualstudio.com/docs/editor/settings-sync) para proporcionar al editor de codespace la misma configuración, métodos abreviados de teclado, fragmentos de código y extensiones que has configurado en la instalación local de Visual Studio Code.

Consulta [Personalizar tu codespace](/es/codespaces/customizing-your-codespace).

## Facturación para Codespaces

Para obtener información sobre precios, almacenamiento y uso de GitHub Codespaces, consulta [facturación de GitHub Codespaces](/es/billing/managing-billing-for-your-products/managing-billing-for-github-codespaces/about-billing-for-github-codespaces).

Si tu cuenta no tiene un método de pago válido en el archivo, el uso se bloqueará una vez que uses la cuota.

Si tienes una forma de pago válida, el gasto puede estar limitado por uno o varios presupuestos. Comprueba los presupuestos establecidos para tu cuenta a fin de asegurarte de que son adecuados para tus necesidades de uso. Consulta [Configuración de presupuestos para controlar el gasto en productos medidos](/es/billing/managing-your-billing/using-budgets-control-spending).

Los costes de GitHub Codespaces siempre se facturan mensualmente, incluso si la cuenta se factura anualmente. Para obtener información sobre cómo los propietarios de organizaciones y los administradores de facturación pueden controlar el límite de gasto de GitHub Codespaces en una organización, consulta [Configuración de presupuestos para controlar el gasto en productos medidos](/es/billing/managing-billing-for-your-products/managing-billing-for-github-codespaces/managing-the-spending-limit-for-github-codespaces).# facturación de GitHub Codespaces

Obtén información sobre los costos de uso de GitHub Codespaces, así como las cuotas de uso mensuales que se incluyen con las cuentas personales de GitHub.

## Procedimiento para medir el uso de GitHub Codespaces

Una instancia de GitHub Codespaces (un "codespace") incurre en dos tipos de cargos.

* **Tiempo de proceso**: tiempo de procesamiento y energía, mientras el codespace está activo.
* **Almacenamiento**: cantidad de espacio en disco que ocupa el codespace o la compilación previa, mientras existe.

Además, los codespaces creados previamente se generan con acciones en minutos, consulta [Acerca de las precompilaciones de GitHub Codespaces](/es/codespaces/prebuilding-your-codespaces/about-github-codespaces-prebuilds).

### Tiempo de proceso

El tiempo de proceso de un codespace es el tiempo que permanece activo. El uso total del tiempo de proceso para cada tipo de procesador se calcula sumando el tiempo utilizado por todos los codespaces facturables a una cuenta determinada. Estos totales se comunican al servicio de facturación diariamente y se cobran mensualmente.

### Volumen de almacenamiento para codespaces

El almacenamiento es una medida basada en el tiempo de la cantidad de almacenamiento que se usa en GB-horas. El almacenamiento medido para codespaces incluye lo siguiente:

* Cualquier archivo que uses en un codespace, como repositorios clonados y archivos de configuración
* Datos cargados en el codespace (por ejemplo, como la entrada o salida del software que se ejecuta en el repositorio)
* Todas las extensiones
* ¿Hay codespaces preconstruidos? Consulta [Acerca de las precompilaciones de GitHub Codespaces](/es/codespaces/prebuilding-your-codespaces/about-github-codespaces-prebuilds)
* Consulta cualquier contenedor de desarrollo personalizado en [Introducción a los contenedores dev](/es/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#creating-a-custom-dev-container-configuration)

### Volumen de almacenamiento para codespaces creados a partir de configuraciones personalizadas

De manera predeterminada, tu codespace se crea a partir de la imagen predeterminada de Linux, también conocida como "configuración de contenedores de desarrollo predeterminada". Si creas un codespace a partir de una configuración de contenedores de desarrollo personalizada, verás un mayor volumen de almacenamiento. Consulta [Introducción a los contenedores dev](/es/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#creating-a-custom-dev-container-configuration).

* **Imagen de Linux predeterminada**: el volumen de almacenamiento para el codespace solo se basa en los archivos del repositorio y los archivos que agregues al codespace.
* **Imagen base personalizada**: el volumen de almacenamiento del codespace incluye el contenedor de desarrollo personalizado, además de todos los archivos del repositorio y el codespace.

Los contenedores basados en la imagen predeterminada no se incluyen en el volumen de almacenamiento, aunque agregues características en la configuración de contenedores de desarrollo. Consulta [Adición de características a un archivo devcontainer.json](/es/codespaces/setting-up-your-project-for-codespaces/configuring-dev-containers/adding-features-to-a-devcontainer-file).

## Uso gratuito y facturado por cuentas personales

Los planes de GitHub para organizaciones y empresas no incluyen una cuota gratuita para GitHub Codespaces.

### Cuota gratuita

Todas las cuentas personales de GitHub incluyen una cuota de tiempo de cómputo gratuito y almacenamiento para GitHub Codespaces. Cualquier uso más allá de los importes incluidos se factura a la cuenta personal.

| Plan de cuenta                        | Almacenamiento por mes | Tiempo de cálculo por mes |
| ------------------------------------- | ---------------------- | ------------------------- |
| GitHub Gratis para cuentas personales | 15 GB al mes           | 120 horas                 |
| GitHub Pro                            | 20 GB al mes           | 180 horas                 |

> \[!NOTE] GitHub Codespaces no está disponible para los repositorios que pertenecen a cuentas de usuario administradas. Para más información, consulta [Acerca de Enterprise Managed Users](/es/enterprise-cloud@latest/admin/identity-and-access-management/using-enterprise-managed-users-for-iam/about-enterprise-managed-users).

Para sugerencias sobre cómo maximizar la utilización del uso permitido, consulta [Sacar el máximo partido del uso incluido](/es/codespaces/troubleshooting/troubleshooting-included-usage).

### Uso superior a la cuota incluida

Si tu cuenta no tiene un método de pago válido en el archivo, el uso se bloqueará una vez que uses la cuota.

Si la reanudación de tu codespace está bloqueada y debes seguir trabajando en los cambios en el codespace, puedes realizar cualquiera de las siguientes acciones:

* Agrega una forma de pago y revisa la configuración del presupuesto para asegurarte de que satisface tus necesidades de uso. Consulta [Configuración de presupuestos para controlar el gasto en productos medidos](/es/billing/tutorials/set-up-budgets#viewing-budgets).
* Exporta los cambios del codespace a una rama. Consulta [Exportar los cambios a una rama](/es/codespaces/troubleshooting/exporting-changes-to-a-branch).
* Espera a que el uso mensual incluido se restablezca al inicio del siguiente ciclo de facturación mensual.

## Pagar por el uso

Pagarás por el uso de Codespaces con el método de pago configurado para tu cuenta de GitHub. Consulta [Administración de la información de facturación y pago](/es/billing/how-tos/set-up-payment/manage-payment-info).

* Para calcular los costes de uso de GitHub Codespaces de pago, usa la [calculadora de precios](https://github.com/pricing/calculator?feature=codespaces) de GitHub.
* Para ver los minutos y el almacenamiento actuales, consulta [Visualización del uso de productos medidos y licencias](/es/billing/managing-billing-for-your-products/viewing-your-product-usage).
* Para optimizar el uso de codespaces:
  * Para cuentas personales, consulta [Sacar el máximo partido del uso incluido](/es/codespaces/troubleshooting/troubleshooting-included-usage)
  * Para las cuentas de organización, consulta [Administración del costo de GitHub Codespaces en su organización](/es/codespaces/managing-codespaces-for-your-organization/managing-the-cost-of-github-codespaces-in-your-organization)

### Precios

El costo de proceso será proporcional al número de núcleos de procesador que tenga el tipo de máquina que elijas para el codespace, tal y como se muestra en la tabla siguiente. Por ejemplo, el coste del proceso de usar un codespace durante una hora en una máquina de 16 núcleos es ocho veces mayor que en una máquina de dos núcleos.

| Componente                   | Tipo de máquina | Unidad de medida | Multiplicador de uso incluido | Precio   |
| ---------------------------- | --------------- | ---------------- | ----------------------------- | -------- |
| Computación de Codespaces    | 2 núcleos       | 1 hora           | 2                             | $0.18    |
| Computación de Codespaces    | 4 núcleos       | 1 hora           | 4                             | $0.36    |
| Computación de Codespaces    | 8 núcleos       | 1 hora           | 8                             | $0.72    |
| Computación de Codespaces    | 16 núcleos      | 1 hora           | 16                            | $1.44    |
| Computación de Codespaces    | 32 núcleos      | 1 hora           | 32                            | $2.88    |
| Almacenamiento de codespaces | Almacenamiento  | 1 GB-mes         | No aplicable                  | 0,07 USD |

## Cómo se asignan los costos a una cuenta facturable

Todo el uso se factura a la cuenta de la persona que ha creado el codespace o a la organización propietaria. Consulta [Selección de quién posee y paga los codespaces de una organización](/es/codespaces/managing-codespaces-for-your-organization/choosing-who-owns-and-pays-for-codespaces-in-your-organization).

Cuando se transfiere un repositorio a otra organización, la propiedad y la responsabilidad de facturación de los codespaces asociados a ese repositorio cambian en función de la configuración de la nueva organización.

Si un usuario se elimina de una organización o repositorio, su codespace se borra automáticamente.

### Repositorios bifurcados

Los codespaces creados a partir de un repositorio bifurcado se facturan a tu cuenta personal, a no ser que el repositorio ascendente (o primario) esté en una organización que te haya permitido (como miembro o colaborador externo) usar codespaces a costa de la organización.

Por ejemplo, considera un miembro o colaborador externo de una organización que ha permitido la facturación de codespaces para ese usuario. Si el usuario tiene permiso para bifurcar un repositorio privado de la organización, posteriormente podrá crear y usar un espacio de código para el nuevo repositorio a cargo de la organización. Esto se debe a que la organización es la propietaria del repositorio primario. Ten en cuenta que el propietario de la organización puede quitar el acceso del usuario al repositorio privado, el repositorio bifurcado y, por lo tanto, también al codespace. El propietario de la organización también puede eliminar el repositorio primario, lo que también eliminaría el repositorio bifurcado. Consulta [Administrar la política de ramificación para tu repositorio](/es/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-forking-policy-for-your-repository).

Si crea precompilaciones para un repositorio bifurcado, el coste de almacenamiento de esas precompilaciones se resta del almacenamiento incluido mensualmente mientras está disponible. Si ha usado todo el almacenamiento incluido y ha configurado la facturación, se facturará su cuenta personal. Esto es cierto incluso cuando la organización que posee el repositorio primario paga los codespaces que crea para una bifurcación.

### Plantillas de GitHub Codespaces

Cualquier organización puede mantener un repositorio de plantillas para su uso con GitHub Codespaces. Al igual que con cualquier otro repositorio de una organización, un codespace creado a partir de un repositorio de plantillas se factura a la organización si esta permite al usuario que crea el codespace hacerlo a expensas de la organización. Si no, el espacio de código se factura al usuario que lo crea.

Si un usuario publica un codespace creado a partir de una plantilla, el codespace se publica en un nuevo repositorio propiedad de la cuenta personal del usuario. Si el codespace se factura actualmente a una organización, la propiedad y la facturación del codespace se transfieren al usuario que lo creó.

Un cuenta de usuario administrada no puede ser el propietario facturable de un codespace. Por lo tanto:

* El cuenta de usuario administrada solo puede crear un codespace a partir de una plantilla si el codespace se factura a una organización.
* El cuenta de usuario administrada no puede publicar un codespace creado a partir de una plantilla en un nuevo repositorio.

## Gestión del presupuesto de GitHub Codespaces

Si tu cuenta no tiene un método de pago válido en el archivo, el uso se bloqueará una vez que uses la cuota.

Si tienes una forma de pago válida, el gasto puede estar limitado por uno o varios presupuestos. Comprueba los presupuestos establecidos para tu cuenta a fin de asegurarte de que son adecuados para tus necesidades de uso. Consulta [Configuración de presupuestos para controlar el gasto en productos medidos](/es/billing/managing-your-billing/using-budgets-control-spending).

También puede recibir notificaciones por correo electrónico cuando el uso incluido de GitHub Codespaces alcance el 90% y 100% durante un período de facturación. Para más información, consulta [Presupuestos y alertas](/es/billing/concepts/budgets-and-alerts#included-usage-alerts).

Si tu cuenta personal, de organización o de empresa usa toda su cuota o presupuesto, ya no podrás crear o reanudar espacios de código facturables a esa cuenta. Sin embargo, todavía puedes exportar cualquier cambio en curso del trabajo a una nueva rama. Para más información, consulta [Exportar los cambios a una rama](/es/codespaces/troubleshooting/exporting-changes-to-a-branch).

## Información adicional

* [Inicio rápido para GitHub Codespaces](/es/codespaces/quickstart)
* [Habilitación o deshabilitación de GitHub Codespaces para su organización](/es/codespaces/managing-codespaces-for-your-organization/enabling-or-disabling-github-codespaces-for-your-organization)
* [Administración del costo de GitHub Codespaces en su organización](/es/codespaces/managing-codespaces-for-your-organization/managing-the-cost-of-github-codespaces-in-your-organization)# Administrar la política de ramificación para tu repositorio

Puedes permitir o evitar la bifurcación de un repositorio privado específico propiedad de una organización.

Un propietario de la organización debe permitir las bifurcaciones de repositorios privados en el nivel de organización para poder permitir o denegar bifurcaciones para un repositorio específico. Para más información, consulta [Administrar la política de bifurcación para tu organización](/es/organizations/managing-organization-settings/managing-the-forking-policy-for-your-organization).

Puedes ayudar a prevenir que se exponga información confidencial deshabilitando la capacidad de bifurcar repositorios en tu organización. Para más información, consulta [Procedimientos recomendados para evitar la pérdida de datos en la organización](/es/code-security/getting-started/best-practices-for-preventing-data-leaks-in-your-organization).

1. En GitHub, navegue hasta la página principal del repositorio.
2. Debajo del nombre del repositorio, haz clic en **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="gear" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> Settings**. Si no puedes ver la pestaña "Configuración", selecciona el menú desplegable **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="More" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg>** y, a continuación, haz clic en **Configuración**.

   ![Captura de pantalla de un encabezado de repositorio en el que se muestran las pestañas. La pestaña "Configuración" está resaltada con un contorno naranja oscuro.](/assets/images/help/repository/repo-actions-settings.png)
3. En "Características", seleccione **Permitir bifurcación**. Si no tiene esta opción, es posible que no tenga permisos para controlar esta configuración. Compruebe con el propietario de la organización que administra el repositorio o con el propietario del repositorio sobre el acceso.

## Información adicional

* [Acerca de los forks](/es/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks)
* [Roles de repositorio para una organización](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization)# Roles de repositorio para una organización

Puedes personalizar el acceso a cada repositorio en tu organización si asignas roles granulares, lo cual le otorga acceso a las personas para las características y tareas que necesitan.

## Roles de repositorio para las organizaciones

Puedes otorgar diferentes niveles de acceso a los miembros organizacionales, colaboradores externos y equipos de personas para los repositorios que pertenezcan a una organización si los asignas con roles. Elige el rol que mejor se adecue a cada función de las personas o los equipos de tu proyecto sin darles más acceso del que necesitan.

Desde el menor hasta el mayo acceso, los roles para un repositorio de organización son:

* **Lectura:** se recomienda para colaboradores que no trabajan en el código, pero que quieren ver el proyecto o hablar sobre él
* **Evaluación de prioridades:** se recomienda para colaboradores que necesitan administrar de forma proactiva problemas, discusiones y solicitudes de incorporación de cambios sin acceso de escritura
* **Escritura:** se recomienda para los colaboradores que insertan cambios activamente en el proyecto
* **Mantenimiento:** se recomienda para los jefes de proyecto que necesiten administrar el repositorio sin acceder a acciones confidenciales o destructivas
* **Administración:** se recomienda para usuarios que necesitan acceso total al proyecto, incluidas acciones confidenciales y destructivas, como administrar la seguridad o eliminar un repositorio

Si en la organización se usa GitHub Enterprise Cloud, puede crear roles de repositorio personalizados. Para más información, consulta [Administrar roles de repositorio personalizados en una organización](/es/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/managing-custom-repository-roles-for-an-organization) en la documentación de GitHub Enterprise Cloud.

Los dueños de las organizaciones pueden configurar permisos base que apliquen a todos los miembros de la misma cuando accedan a cualquiera de los repositorios que le pertenezcan a dicha organización. Para más información, consulta [Establecimiento de permisos base para una organización](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/setting-base-permissions-for-an-organization#setting-base-permissions).

Los propietarios de la organización también pueden decidir limitar más el acceso a determinados parámetros y acciones de la organización. Para más información sobre las opciones de configuración específicas, consulte [Administrar configuraciones de la organización](/es/organizations/managing-organization-settings).

Adicionalmente a administrar los ajustes a nivel organizacional, los propietarios de organización tienen acceso administrativo a cada repositorio que pertenece a la organización. Para más información, consulta [Roles en una organización](/es/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization).

> \[!WARNING]
> Cuando alguien agrega una clave de implementación a un repositorio, cualquier usuario que tenga la clave privada puede leer o escribir en el repositorio (según la configuración de la clave), incluso si luego se le elimina de la organización.

## Permisos para cada rol

Algunas de las características siguientes se limitan a las organizaciones que utilizan GitHub Enterprise Cloud. Para más información sobre cómo probar GitHub Enterprise Cloud de forma gratuita, consulta [Configuración de una versión de prueba de GitHub Enterprise Cloud](/es/enterprise-cloud@latest/admin/overview/setting-up-a-trial-of-github-enterprise-cloud).

> \[!NOTE]
> Los roles necesarios para usar las características de seguridad se enumeran en [Requisitos de acceso para las características de seguridad](#access-requirements-for-security-features) a continuación.

<div class="ghd-tool rowheaders">

| Acción del repositorio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Lectura | Evaluación de prioridades | Escritura | Mantener | Administrador |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-----: | :-----------------------: | :-------: | :------: | :-----------: |
| Administrar el acceso [individual](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/managing-an-individuals-access-to-an-organization-repository), de [equipo](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/managing-team-access-to-an-organization-repository) y de [colaborador externo](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization) al repositorio |         |                           |           |          |               |

```
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
```

\| Extraer desde los repositorios asignados de la persona o el equipo | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Bifurcar los repositorios asignados de la persona o el equipo | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Editar y eliminar sus propios comentarios | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Abrir propuestas | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Cerrar propuestas que abrieron ellos mismos | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Reabrir propuestas que cerraron ellos mismos | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Recibir la asignación de una propuesta | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Enviar solicitudes de extracción desde bifurcaciones de repositorios asignados del equipo | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Enviar revisiones o solicitudes de extracción](/es/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Aprobar o solicitar cambios en una solicitud de incorporación de cambios con las revisiones necesarias](/es/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/approving-a-pull-request-with-required-reviews) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Aplicar cambios sugeridos](/es/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request) a solicitudes de incorporación de cambios | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Ver lanzamientos publicados | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Ver ejecuciones de flujo de trabajo de [GitHub Actions](/es/actions/managing-workflow-runs) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Editar los wikis en los repositorios públicos | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Editar los wikis en los repositorios privados | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| [Notificar contenido abusivo o con spam](/es/communities/maintaining-your-safety-on-github/reporting-abuse-or-spam) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Aplicar/descartar etiquetas | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Crear, editar, borrar etiquetas | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Elegir, reabrir y asignar todas las propuestas y solicitudes de extracción | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Habilitar e inhabilitar la fusión mediante combinación automática en una solicitud de incorporación de cambios](/es/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-auto-merge-for-pull-requests-in-your-repository) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Crear, editar, eliminar hitos | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Aplicar hitos | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Marcar [incidencias y solicitudes de incorporación de cambios duplicadas](/es/issues/tracking-your-work-with-issues/marking-issues-or-pull-requests-as-a-duplicate)| <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Solicitar [revisiones de solicitudes de incorporación de cambios](/es/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/requesting-a-pull-request-review) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Combinar una [solicitud de incorporación de cambios](/es/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/about-pull-request-merges) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Subir a (escribir en) los repositorios asignados de la persona o el equipo | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Editar y eliminar comentarios sobre confirmaciones, solicitudes de extracción y propuestas de cualquier persona | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Ocultar los comentarios de cualquier persona](/es/communities/moderating-comments-and-conversations/managing-disruptive-comments) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Bloquear conversaciones](/es/communities/moderating-comments-and-conversations/locking-conversations) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Problemas de transferencia (consulta [Transferir una incidencia a otro repositorio](/es/issues/tracking-your-work-with-issues/transferring-an-issue-to-another-repository) para más detalles) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Actuar como propietario del código designado para un repositorio](/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Marcar un borrador de solicitud de incorporación de cambios como listo para revisión](/es/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/changing-the-stage-of-a-pull-request) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Convertir una solicitud de incorporación de cambios en borrador](/es/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/changing-the-stage-of-a-pull-request) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Crear [comprobaciones de estado](/es/pull-requests/collaborating-with-pull-requests/collaborating-on-repositories-with-code-quality-features/about-status-checks) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Crear, editar, ejecutar, volver a ejecutar y cancelar flujos de trabajo de [GitHub Actions](/es/actions) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\|  |
\| Creación, actualización y eliminación de secretos de [GitHub Actions](/es/actions/security-guides/using-secrets-in-github-actions) en GitHub.com | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Creación, actualización y eliminación de secretos de [GitHub Actions](/es/rest/actions/secrets) mediante la API rest | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Crear, actualizar y eliminar variables [GitHub Actions](/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables) en GitHub.com | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Creación, actualización y eliminación de variables [GitHub Actions](/es/rest/actions/variables) mediante la API REST | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Crear y editar lanzamientos | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Ver lanzamientos en borrador | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Editar la descripción de un repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| [Ver e instalar paquetes](/es/packages/learn-github-packages) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Publicar paquetes](/es/packages/learn-github-packages/publishing-a-package) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Borrar y restaurar paquetes](/es/packages/learn-github-packages/deleting-and-restoring-a-package) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Administrar [temas](/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Habilitar wikis y restringir editores de wikis | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Configurar [combinaciones de solicitudes de incorporación de cambios](/es/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Configurar [un origen de publicación para GitHub Pages](/es/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Ver la [configuración de exclusión de contenido](/es/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-github-copilot-features-in-your-organization/about-content-exclusions-for-github-copilot) de GitHub Copilot | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Administración de [reglas de protección de rama](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule) y [conjuntos de reglas de repositorio](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Ver los [conjuntos de reglas de un repositorio](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Insertar en ramas protegidas](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)</br>No se aplica a los conjuntos de reglas, ya que tienen un modelo de omisión diferente. Consulta [Concesión de permisos de omisión para tu rama o el conjunto de reglas de etiqueta](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/creating-rulesets-for-a-repository#granting-bypass-permissions-for-your-branch-or-tag-ruleset). | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Fusionar solicitudes de extracción en las ramas protegidas, incluso si no existen revisiones en aprobación | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| [Crear y editar las tarjetas sociales de un repositorio](/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Limitar las [interacciones en un repositorio](/es/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository)| <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Eliminar una incidencia (consulta [Eliminar una incidencia](/es/issues/tracking-your-work-with-issues/deleting-an-issue)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Definir propietarios del código para un repositorio](/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Agregar un repositorio a un equipo (consulta [Administrar el acceso de equipo a un repositorio de la organización](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-team-access-to-an-organization-repository#giving-a-team-access-to-a-repository) para más detalles) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Administrar el acceso de un colaborador externo a un repositorio](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Cambiar la visibilidad de un repositorio](/es/organizations/managing-organization-settings/restricting-repository-visibility-changes-in-your-organization) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Convertir un repositorio en una plantilla (consultar [Crear un repositorio de plantilla](/es/repositories/creating-and-managing-repositories/creating-a-template-repository)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Cambiar los parámetros de un repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Administrar el acceso de un equipo o un colaborador al repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Editar la rama predeterminada de un repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Cambiar el nombre de la rama predeterminada del repositorio (consulta [Renombrar una rama](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/renaming-a-branch)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Cambiar el nombre de una rama distinta de la rama predeterminada del repositorio (consulta [Renombrar una rama](/es/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/renaming-a-branch)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| Administrar webhooks y desplegar llaves | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Administrar la directiva de bifurcación de un repositorio](/es/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-forking-policy-for-your-repository) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Transferir repositorios a la organización](/es/organizations/managing-organization-settings/restricting-repository-creation-in-your-organization) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Eliminar o transferir repositorios fuera de la organización](/es/organizations/managing-organization-settings/setting-permissions-for-deleting-or-transferring-repositories) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Archivar repositorios](/es/repositories/archiving-a-github-repository/archiving-repositories) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Mostrar el botón de un patrocinador (consulta [Mostrando un botón de patrocinador en tu repositorio](/es/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/displaying-a-sponsor-button-in-your-repository)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Crear referencias de vínculo automático a recursos externos, como Jira o Zendesk (consulta [Configurar enlaces automáticos para referenciar recursos externos](/es/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-autolinks-to-reference-external-resources)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Habilitar GitHub Discussions](/es/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/enabling-or-disabling-github-discussions-for-a-repository) en un repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Crear y editar categorías](/es/discussions/managing-discussions-for-your-community/managing-categories-for-discussions) para GitHub Discussions | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Mover un debate a otra categoría](/es/discussions/managing-discussions-for-your-community/managing-discussions) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Transferir un debate](/es/discussions/managing-discussions-for-your-community/managing-discussions) a un nuevo repositorio| <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Administrar debates fijados](/es/discussions/managing-discussions-for-your-community/managing-discussions) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Bloquear y desbloquear los debates](/es/discussions/managing-discussions-for-your-community/moderating-discussions) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Convertir las incidencias en debates individualmente](/es/discussions/managing-discussions-for-your-community/moderating-discussions) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Crear debates y comentar los debates existentes](/es/discussions/collaborating-with-your-community-using-discussions/participating-in-a-discussion) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Borrar un debate](/es/discussions/managing-discussions-for-your-community/managing-discussions#deleting-a-discussion) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| [Crear codespaces](/es/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository?tool=webui) para repositorios privados | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Crear codespaces](/es/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository?tool=webui) para repositorios privados con [acceso a secretos de codespaces](/es/codespaces/managing-codespaces-for-your-organization/managing-development-environment-secrets-for-your-repository-or-organization?tool=webui) | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="No" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="No" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Crear codespaces](/es/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository?tool=webui) para repositorios públicos<br>(los usuarios con acceso de solo lectura solo pueden crear codespaces corriendo con los gastos) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Edición de los valores de propiedad personalizados para el repositorio | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |

</div>

### Requisitos de acceso para las características de seguridad

En esta sección, puedes encontrar el acceso que se requiere para las características de seguridad, tales como las características de GitHub Advanced Security.

> \[!NOTE]
> Los escritores y mantenedores de los repositorios solo pueden ver directamente la información de las alertas de examen de secretos de sus propias confirmaciones. No pueden acceder a la vista de lista de alertas.

<div class="ghd-tool rowheaders">

| Acción del repositorio                                                                                                                                | Lectura | Evaluación de prioridades | Escritura | Mantener | Administrador |
| :---------------------------------------------------------------------------------------------------------------------------------------------------- | :-----: | :-----------------------: | :-------: | :------: | :-----------: |
| Recibe [Dependabot alerts para las dependencias no seguras](/es/code-security/dependabot/dependabot-alerts/about-dependabot-alerts) en un repositorio |         |                           |           |          |               |

```
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | 
          <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | 
          <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | 
          <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
```

\| [Ignorar Dependabot alerts](/es/code-security/dependabot/dependabot-alerts/viewing-and-updating-dependabot-alerts) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\|  |
\| Creación de [avisos de seguridad](/es/code-security/security-advisories/working-with-repository-security-advisories/about-repository-security-advisories) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| Administrar el acceso a las características de GitHub Advanced Security (consulta [Administrar la configuración de seguridad y análisis de su organización](/es/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/managing-security-and-analysis-settings-for-your-organization)) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\| [Activación de la gráfica de dependencias](/es/code-security/supply-chain-security/understanding-your-software-supply-chain/exploring-the-dependencies-of-a-repository) para un repositorio privado <!--Set at site-level for GHES --> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\|  |
\|  |
\| [Visualización de alertas del code scanning en las solicitudes de incorporación de cambios](/es/code-security/code-scanning/managing-code-scanning-alerts/triaging-code-scanning-alerts-in-pull-requests) | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Enumeración, descarte y eliminación de alertas de code scanning](/es/code-security/code-scanning/managing-code-scanning-alerts/resolving-code-scanning-alerts) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> |
\| [Visualización y descarte de alertas de detección de secretos en un repositorio](/es/code-security/secret-scanning/managing-alerts-from-secret-scanning) | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-x" aria-label="No">✗</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | <span role="img" class="octicon-bg-check" aria-label="Yes">✓</span> | |
\|  |

</div>

## Información adicional

* [Administración del acceso de usuario a los repositorios de la organización](/es/organizations/managing-user-access-to-your-organizations-repositories)
* [Agregar colaboradores externos a los repositorios en tu organización](/es/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization)# Acerca de las alertas Dependabot

Dependabot alerts le ayudará a encontrar y corregir las dependencias vulnerables antes de que se conviertan en riesgos de seguridad.

El software a menudo se basa en paquetes de varios orígenes, creando relaciones de dependencia que pueden introducir vulnerabilidades de seguridad sin saberlo. Cuando tu código depende de paquetes con vulnerabilidades de seguridad conocidas, te conviertes en un objetivo para los atacantes que buscan aprovecharse de tu sistema, pudiendo obtener acceso a tu código, datos, clientes o colaboradores.
Dependabot alerts notifique las dependencias vulnerables para que pueda actualizar a versiones seguras y proteger el proyecto.

## Cuando Dependabot envía alertas

```
          Dependabot examina la rama predeterminada del repositorio y envía alertas cuando:
```

* Se agrega una nueva vulnerabilidad a la GitHub Advisory Database
* Cambia el gráfico de dependencias, por ejemplo, al insertar confirmaciones que actualizan paquetes o versiones.

Para conocer los ecosistemas admitidos, consulte [Ecosistemas de paquetes que soportan el gráfico de dependencias](/es/code-security/supply-chain-security/understanding-your-software-supply-chain/dependency-graph-supported-package-ecosystems#supported-package-ecosystems).

## Descripción de las alertas

Cuando GitHub detecta una dependencia vulnerable, aparece una Dependabot alerta en la pestaña del **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-shield" aria-label="shield" role="img"><path d="M7.467.133a1.748 1.748 0 0 1 1.066 0l5.25 1.68A1.75 1.75 0 0 1 15 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.697 1.697 0 0 1-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 0 1 1.217-1.667Zm.61 1.429a.25.25 0 0 0-.153 0l-5.25 1.68a.25.25 0 0 0-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.196.196 0 0 0 .154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.251.251 0 0 0-.174-.237l-5.25-1.68ZM8.75 4.75v3a.75.75 0 0 1-1.5 0v-3a.75.75 0 0 1 1.5 0ZM9 10.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path></svg> Security and quality** repositorio y el gráfico de dependencias. Cada alerta incluye:

* Vínculo al archivo afectado
* Detalles sobre la vulnerabilidad y su gravedad
* Información sobre una versión fija (cuando está disponible)

Para obtener información sobre cómo ver y administrar alertas, consulte [Visualización y actualización de alertas de Dependabot](/es/code-security/dependabot/dependabot-alerts/viewing-and-updating-dependabot-alerts).

## ¿Quién puede habilitar alertas?

Los administradores de repositorios y los propietarios de la organización pueden habilitar Dependabot alerts para sus repositorios y organizaciones. Cuando se habilita, GitHub genera inmediatamente el gráfico de dependencias y crea alertas para las dependencias vulnerables que identifica.
Los administradores del repositorio pueden conceder acceso a personas o equipos adicionales.

Consulta [Configuración de alertas de Dependabot](/es/code-security/dependabot/dependabot-alerts/configuring-dependabot-alerts).

## Propiedad y asignaciones de alertas

Los usuarios con acceso de escritura o superior pueden asignar Dependabot alerts a colaboradores del repositorio, equipos o Copilot para establecer una propiedad clara para la corrección de vulnerabilidades. Las asignaciones ayudan a realizar un seguimiento de quién es responsable de cada alerta y evitar que se pasen por alto las vulnerabilidades.

Cuando se asigna una alerta, el receptor recibe una notificación y la alerta muestra su nombre en la lista de alertas. Puede filtrar las alertas por parte del asignado para realizar un seguimiento del progreso. La asignación de una alerta a Copilot genera automáticamente una corrección y abre una solicitud de incorporación de cambios en borrador para revisión.

Para obtener información sobre cómo asignar alertas, consulte [Visualización y actualización de alertas de Dependabot](/es/code-security/how-tos/manage-security-alerts/manage-dependabot-alerts/viewing-and-updating-dependabot-alerts#viewing-and-prioritizing-dependabot-alerts).

## Funcionamiento de las notificaciones de alerta

De forma predeterminada, GitHub envía notificaciones por correo electrónico sobre las nuevas alertas a las personas que:

* Tener permisos de escritura, mantenimiento o administrador en un repositorio
* Está viendo el repositorio y ha habilitado las notificaciones para las alertas de seguridad o para toda la actividad en el repositorio

Puede invalidar el comportamiento predeterminado si elige el tipo de notificaciones que desea recibir o desactiva las notificaciones por completo en la página de configuración de las notificaciones de usuario en <https://github.com/settings/notifications>.

Independientemente de las preferencias de notificación, cuando Dependabot se habilita por primera vez, GitHub no envía notificaciones para todas las dependencias vulnerables que se encuentran en el repositorio. En su lugar, recibirá notificaciones para las nuevas dependencias vulnerables identificadas después de que Dependabot sea habilitado, si sus preferencias de notificación lo permiten.

Si le preocupa recibir demasiadas notificaciones, se recomienda aprovechar Evaluación de prioridades automática de Dependabot para descartar automáticamente las alertas de bajo riesgo. Las reglas se aplican antes de enviar las notificaciones de alerta, por lo que las alertas que se descartan automáticamente tras la creación no envían notificaciones. Consulta [Acerca de Evaluación de prioridades automática de Dependabot](/es/code-security/dependabot/dependabot-auto-triage-rules/about-dependabot-auto-triage-rules).

Como alternativa, puede suscribirse al resumen semanal por correo electrónico, o incluso desactivar completamente las notificaciones mientras mantiene Dependabot alerts habilitado.

## Limitaciones

```
          Dependabot alerts tienen algunas limitaciones:
```

* Las alertas no pueden detectar todos los problemas de seguridad. Revise siempre las dependencias y mantenga actualizados los archivos de manifiesto y bloqueo para una detección precisa.
* Las nuevas vulnerabilidades pueden tardar tiempo en aparecer en las GitHub Advisory Database y activar alertas.
* Solo los avisos revisados por GitHub activan alertas.
* Dependabot no examina los repositorios archivados.
* Para GitHub Actions, las alertas solo se generan para las acciones que usan el control de versiones semántico, no el control de versiones SHA.

  ```
          GitHub nunca divulga públicamente las vulnerabilidades de ningún repositorio. 
  ```

## Lectura adicional

* [Alertas de malware de Dependabot](/es/code-security/concepts/supply-chain-security/dependabot-malware-alerts)
* [Visualización y actualización de alertas de Dependabot](/es/code-security/dependabot/dependabot-alerts/viewing-and-updating-dependabot-alerts)
* [Sobre las actualizaciones de seguridad de Dependabot](/es/code-security/dependabot/dependabot-security-updates/about-dependabot-security-updates)
* [Auditoría de alertas de seguridad](/es/code-security/getting-started/auditing-security-alerts)# Acerca de Evaluación de prioridades automática de Dependabot

Controla cómo Dependabot maneja las alertas de seguridad, incluyendo el filtrado, la omisión, el posponer o el desencadenar actualizaciones de seguridad.

<!-- TRANSLATION_FALLBACK prop=markdown type=ParseError line=1 col=1 msg="tag {%- ifversion fpt %} not closed" -->
## About Dependabot auto-triage rules

Dependabot auto-triage rules allow you to instruct Dependabot to automatically triage Dependabot alerts and Dependabot malware alerts. You can use auto-triage rules to:

* Automatically dismiss or snooze certain alerts
* Specify the Dependabot alerts you want Dependabot to open pull requests for

Rules are applied before alert notifications are sent, so enabling rules that auto-dismiss low-risk alerts will help reduce notification noise.

There are two types of Dependabot auto-triage rules:

* GitHub presets
* Custom auto-triage rules

### About GitHub presets

GitHub presets are rules curated by GitHub that are available for all repositories.

#### Dismiss low impact issues for development-scoped dependencies

The `Dismiss low impact issues for development-scoped dependencies` rule is a GitHub preset that auto-dismisses certain types of vulnerabilities that are found in npm dependencies used in development. These alerts cover cases that feel like false alarms to most developers as the associated vulnerabilities:

* Are unlikely to be exploitable in a developer (non-production or runtime) environment.
* May relate to resource management, programming and logic, and information disclosure issues.
* At worst, have limited effects like slow builds or long-running tests.
* Are not indicative of issues in production.

The rule is enabled by default for public repositories and can be opted into for private repositories. For instructions, see [Enabling the `Dismiss low impact issues for development-scoped dependencies` rule for your private repository](/en/code-security/dependabot/dependabot-auto-triage-rules/using-github-preset-rules-to-prioritize-dependabot-alerts#enabling-the-dismiss-low-impact-issues-for-development-scoped-dependencies-rule-for-your-private-repository).

For more information about the criteria used by the rule, see [CWEs used by GitHub's preset Dependabot rules](/en/code-security/reference/supply-chain-security/criteria-for-preset-rules).

#### Dismiss package malware alerts

The `Dismiss package malware alerts` rule is a GitHub preset that auto-dismisses alerts that flag all versions of a package as malicious. If your project depends on an **internal** package with the same ecosystem and name as a malicious **public** package, Dependabot can generate a false positive alert, which the rule then auto-dismisses.

> \[!IMPORTANT]
> Be aware that if a contributor adds a dependency that is truly malicious across all versions, this rule will auto-dismiss the related alert.

The `Dismiss package malware alerts` rule is disabled by default, but can be enabled for any repository using Dependabot malware alerts.

### About custom auto-triage rules

> \[!NOTE]
>
> Custom auto-triage rules for Dependabot alerts are available on public repositories and on any organization-owned repositories in GitHub Team with [GitHub Code Security](/en/get-started/learning-about-github/about-github-advanced-security) enabled.

With custom auto-triage rules, you can create your own rules to automatically dismiss or reopen alerts based on targeted metadata, such as severity, package name, CWE, and more. You can also specify which Dependabot alerts you want Dependabot to open pull requests for. For more information, see [Customizing auto-triage rules to prioritize Dependabot alerts](/en/code-security/dependabot/dependabot-auto-triage-rules/customizing-auto-triage-rules-to-prioritize-dependabot-alerts).

You can create custom rules from the **Settings** tab of the repository, provided the repository belongs to an organization that has a license for GitHub Code Security or GitHub Advanced Security. For more information, see [Adding custom auto-triage rules to your repository](/en/code-security/dependabot/dependabot-auto-triage-rules/customizing-auto-triage-rules-to-prioritize-dependabot-alerts#adding-custom-auto-triage-rules-to-your-repository).

### About auto-dismissing alerts

Whilst you may find it useful to use auto-triage rules to auto-dismiss alerts, you can still reopen auto-dismissed alerts and filter to see which alerts have been auto-dismissed. For more information, see [Managing alerts that have been automatically dismissed by a Dependabot auto-triage rule](/en/code-security/dependabot/dependabot-auto-triage-rules/managing-automatically-dismissed-alerts).

Additionally, auto-dismissed alerts are still available for reporting and reviewing, and can be auto-reopened if the alert metadata changes, for example:

* If you change the scope of a dependency from development to production.
* If GitHub modifies certain metadata for the related advisory.

Auto-dismissed alerts are defined by the `resolution:auto-dismiss` close reason. Automatic dismissal activity is included in alert webhooks, REST and GraphQL APIs, and the audit log. For more information, see [REST API endpoints for Dependabot alerts](/en/rest/dependabot/alerts), and the "`repository_vulnerability_alert`" section in [Reviewing the audit log for your organization](/en/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization#repository_vulnerability_alert-category-actions).

## Next steps

To get started with Dependabot auto-triage rules, see [Using GitHub preset rules to prioritize Dependabot alerts](/en/code-security/dependabot/dependabot-auto-triage-rules/using-github-preset-rules-to-prioritize-dependabot-alerts).

To customize your auto-triage experience, see [Customizing auto-triage rules to prioritize Dependabot alerts](/en/code-security/dependabot/dependabot-auto-triage-rules/customizing-auto-triage-rules-to-prioritize-dependabot-alerts).# Acerca de GitHub Advanced Security

GitHub hace que las características de seguridad adicionales estén disponibles para los clientes que compran GitHub Code Security o GitHub Secret Protection.

<!-- TRANSLATION_FALLBACK prop=markdown type=ParseError line=24 col=1 msg="tag {% ifversion ghas-products %} not closed" -->
## About GitHub Advanced Security products

GitHub has many features that help you improve and maintain the quality of your code. Some of these are included in all plans, such as dependency graph and Dependabot alerts.

Other security features require you to purchase one of GitHub's Advanced Security products:

* **GitHub Secret Protection**, which includes features that help you detect and prevent secret leaks, such as secret scanning and push protection.
* **GitHub Code Security**, which includes features that help you find and fix vulnerabilities, like code scanning, premium Dependabot features, and dependency review.

Some of these features, such as code scanning and secret scanning, are enabled for public repositories by default. To run the feature on your private or internal repositories, you must purchase the relevant GitHub Advanced Security product.

You must be on a GitHub Team or GitHub Enterprise plan in order to purchase GitHub Code Security or GitHub Secret Protection. For more information, see [GitHub's plans](/en/get-started/learning-about-github/githubs-plans) and [GitHub Advanced Security license billing](/en/billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/about-billing-for-github-advanced-security).

## GitHub Code Security

You get the following features with GitHub Code Security:

* **Code scanning**: Search for potential security vulnerabilities and coding errors in your code using CodeQL or a third-party tool.

* **CodeQL CLI**: Run CodeQL processes locally on software projects or to generate code scanning results for upload to GitHub.

* **Copilot Autofix**: Get automatically generated fixes for code scanning alerts.

* **Security campaigns**: Reduce security debt at scale.

* **Custom auto-triage rules for Dependabot**: Manage your Dependabot alerts at scale, by automating which alerts you want to ignore, snooze, or trigger a Dependabot security update for.

* **Dependency review**: Show the full impact of changes to dependencies and see details of any vulnerable versions before you merge a pull request.

* **Security overview**: Understand the distribution of risk across your organization.

The table below summarizes the availability of GitHub Code Security features for public and private repositories.

<div class="ghd-tool rowheaders">

|                          | Public repository <br>without GitHub Code Security                                                                                                                                                                                                                                                                                                                                                                       | Private repository <br>without GitHub Code Security                                                                                                                                                                                                                                                                                                                                                                      | Public or private repository <br>with GitHub Code Security                                                                                                                                                                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Code scanning            | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg>                                                                                                       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
| CodeQL CLI               | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg>                                                                                                       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Copilot Autofix          | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg>                                                                                                       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
|                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Security campaigns       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Custom auto-triage rules | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
| Dependency review        | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
| Security overview        | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |

</div>

For more information about features, see [GitHub security features](/en/code-security/getting-started/github-security-features).

## GitHub Secret Protection

You get the following features with GitHub Secret Protection:

* **Secret scanning**: Detect secrets, for example keys and tokens, that have been checked into a repository and receive alerts.
* **Push protection**: Prevent secret leaks before they happen by blocking commits containing secrets.
* **Copilot secret scanning**: Leverage AI to detect unstructured credentials, such as passwords, that have been checked into a repository.
* **Custom patterns**: Detect and prevent leaks for organization-specific secrets.
* **Delegated bypass for push protection** and **Delegated alert dismissal**:  Implement an approval process for better control over who in your enterprise can perform sensitive actions, supporting governance at scale.
* **Security campaigns**: Remediate exposed secrets at scale by creating a campaign and collaborating to fix them.
* **Security overview**: Understand the distribution of risk across your organization.

The table below summarizes the availability of GitHub Secret Protection features for public and private repositories.

<div class="ghd-tool rowheaders">

|                                      | Public repository <br>without GitHub Secret Protection                                                                                                                                                                                                                                                                                                                                                                   | Private repository <br>without GitHub Secret Protection                                                                                                                                                                                                                                                                                                                                                                  | Public or private repository <br>with GitHub Secret Protection                                                                                                                                                                                                                                                     |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Secret scanning                      | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg>                                                                                                       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
| Push protection                      | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg>                                                                                                       | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                                      |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Copilot secret scanning              | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                                      |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Custom patterns                      | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
| Delegated bypass for push protection | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                                      |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Security campaigns                   | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |
|                                      |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                    |
| Security overview                    | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-x" aria-label="No" role="img"><path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path></svg> | <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-check" aria-label="Yes" role="img"><path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path></svg> |

</div>

For more information about individual features, see [GitHub security features](/en/code-security/getting-started/github-security-features).

## Run a free security risk assessment

<a href="https://github.com/get_started?with=risk-assessment&ref_product=code-scanning&ref_type=engagement&ref_style=button" target="_blank" class="btn btn-primary mt-3 mr-3 no-underline"><span>Get started with security risk assessments</span> <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-link-external" aria-label="link external icon" role="img"><path d="M3.75 2h3.5a.75.75 0 0 1 0 1.5h-3.5a.25.25 0 0 0-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-3.5a.75.75 0 0 1 1.5 0v3.5A1.75 1.75 0 0 1 12.25 14h-8.5A1.75 1.75 0 0 1 2 12.25v-8.5C2 2.784 2.784 2 3.75 2Zm6.854-1h4.146a.25.25 0 0 1 .25.25v4.146a.25.25 0 0 1-.427.177L13.03 4.03 9.28 7.78a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0 1 10.604 1Z"></path></svg></a>

Organizations on GitHub Team and GitHub Enterprise can run free security risk assessments to understand their exposure to security vulnerabilities:

* **Secret leaks**: Scan your organization for leaked secrets and see how many could have been prevented by GitHub Secret Protection. See [About secret security with GitHub](/en/code-security/concepts/secret-security/about-secret-security-with-github#secret-risk-assessment).

* **Code vulnerabilities**: Scan up to 20 of your most active repositories and see how many vulnerabilities could be automatically fixed with Copilot Autofix if you enable GitHub Code Security. See [Code security risk assessment](/en/code-security/concepts/code-scanning/code-security-risk-assessment).

## Deploying GitHub Code Security and GitHub Secret Protection

To learn about what you need to know to plan your deployment of GitHub Code Security and GitHub Secret Protection at a high level and to review the rollout phases we recommended, see [Adopting GitHub Advanced Security at scale](/en/code-security/adopting-github-advanced-security-at-scale).

## Enabling features

You can quickly enable security features at scale with a security configuration, a collection of security enablement settings you can apply to repositories in an organization. You can customize Advanced Security features at the organization level with global settings. See [About enabling security features at scale](/en/code-security/securing-your-organization/introduction-to-securing-your-organization-at-scale/about-enabling-security-features-at-scale).

If you are on a GitHub Team or GitHub Enterprise plan, license use for the entire team or enterprise is shown on your license page. See [Viewing your usage of metered products and licenses](/en/billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/viewing-your-github-advanced-security-usage).

## Managing GitHub Advanced Security

Enterprise owners can manage GitHub Advanced Security licensing and access for their enterprise, including disabling GitHub Advanced Security across all repositories and preventing future re-enablement. See [Managing volume licenses for GitHub Advanced Security](/en/billing/how-tos/products/manage-ghas-licenses#disabling-github-advanced-security-across-your-enterprise).

For information about managing your GitHub Advanced Security license, see [Managing your paid use of Advanced Security](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/managing-your-github-advanced-security-license-usage).

## About GitHub Advanced Security Certification

You can highlight your knowledge by earning a GitHub Advanced Security certificate with GitHub Certifications. The certification validates your expertise in vulnerability identification, workflow security, and robust security implementation. See [About GitHub Certifications](/en/get-started/showcase-your-expertise-with-github-certifications/about-github-certifications).

## About GitHub Advanced Security with Azure Repos

If you want to use GitHub Advanced Security with Azure Repos, see [GitHub Advanced Security & Azure DevOps](https://resources.github.com/topics/github-advanced-security/) in our resources site. For documentation, see [Configure GitHub Advanced Security for Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features) in Microsoft Learn.

## Further reading

* [GitHub security features](/en/code-security/getting-started/github-security-features)
* [GitHub public roadmap](https://github.com/github/roadmap)🌞 Morning                1550 commits        █████░░░░░░░░░░░░░░░░░░░░   21.41 % 
🌆 Daytime                1040 commits        ████░░░░░░░░░░░░░░░░░░░░░   14.37 % 
🌃 Evening                1027 commits        ████░░░░░░░░░░░░░░░░░░░░░   14.19 % 
🌙 Night                  3621 commits        █████████████░░░░░░░░░░░░   50.03 % <?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom" xmlns:dc="http://purl.org/dc/elements/1.1/">
  <channel>
    <title>The ReadME Project</title>
    <link>https://github.com/readme</link>
    <atom:link href="https://github.com/readme.rss" rel="self" type="application/rss+xml"/>
    <image>
      <title>The ReadME Project</title>
      <url>https://github.githubassets.com/assets/readme-project-1b8ad1b2a413.jpg</url>
      <link>https://github.com/readme</link>
    </image>
    <description>The ReadME Project amplifies the voices of the open source community: the maintainers, developers, and teams whose contributions move the world forward every day.</description>
    <item>
      <title>Coding accessibility: Software by the blind, for the blind</title>
      <link>https://github.com/readme/featured/nvda-coding-accessibility-software-blind</link>
      <description>NVDA and OSARA provide access to information, employment, community, and more, as well as empower a new generation to build a more accessible world.</description>
      <pubDate>Thu, 16 May 2024 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/nvda-coding-accessibility-software-blind</guid>
    </item>
    <item>
      <title>Coding accessibility: How Della found her voice with open source AAC</title>
      <link>https://github.com/readme/featured/open-source-aac</link>
      <description>Discover FreeSpeechAAC, an open source assistive communication tool thoughtfully designed by Archer Calder, his nonspeaking sister Della, and the open source community. </description>
      <pubDate>Sun, 3 Dec 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/open-source-aac</guid>
    </item>
    <item>
      <title>A beginner’s guide to running and managing custom CodeQL queries</title>
      <link>https://github.com/readme/guides/custom-codeql-queries</link>
      <description>Learn how to transform your code with custom CodeQL queries that empower you to surface security vulnerabilities and discover new insights.
</description>
      <pubDate>Tue, 24 Oct 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/custom-codeql-queries</guid>
    </item>
    <item>
      <title>Scaling standards and community in your organization</title>
      <link>https://github.com/readme/guides/federated-model</link>
      <description>Learn how to apply open source community ideas to your organization to spread standards and best practices without sacrificing autonomy and innovation.</description>
      <pubDate>Tue, 24 Oct 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/federated-model</guid>
    </item>
    <item>
      <title>Coding accessibility: Building autonomy with AI</title>
      <link>https://github.com/readme/featured/accessibility-artificial-intelligence</link>
      <description>After bringing Braille to the digital world in the 1980s and creating the first screen reader for the web in the 1990s, Dr. Chieko Asakawa is now working on an AI-enabled suitcase—and says collaboration is the key to more accessible tech.</description>
      <pubDate>Tue, 10 Oct 2023 17:45:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/accessibility-artificial-intelligence</guid>
    </item>
    <item>
      <title>Treat accessibility issues as bugs, not feature requests</title>
      <link>https://github.com/readme/guides/fix-accessibility-bugs</link>
      <description>It takes leadership to treat accessibility issues as bugs, and prioritize them before a project is released. Learn how they do it at Drupal.
</description>
      <pubDate>Tue, 8 Aug 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/fix-accessibility-bugs</guid>
    </item>
    <item>
      <title>Provisioning self-hosted GitHub Actions runners on demand</title>
      <link>https://github.com/readme/guides/github-runners-philips</link>
      <description>Unlock the secrets of scaling GitHub self-hosted runners in the enterprise cloud. Dive into Philips' method with Terraform and GitHub Actions to elevate your CI/CD game.</description>
      <pubDate>Tue, 8 Aug 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/github-runners-philips</guid>
    </item>
    <item>
      <title>Is Laravel the happiest developer community on the planet?</title>
      <link>https://github.com/readme/featured/laravel-community</link>
      <description>How the PHP framework Laravel prioritizes developer experience by focusing on details and avoiding the hype cycle</description>
      <pubDate>Tue, 8 Aug 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/laravel-community</guid>
    </item>
    <item>
      <title>Realizing potential with AI</title>
      <link>https://github.com/readme/stories/anton-mirhorodchenko</link>
      <description>Neither keyboards nor voice-to-text work well for Anton, a developer with cerebral palsy. He uses AI and LLMs to pursue his passion for programming and shows others how they can harness these technologies to accomplish more.</description>
      <pubDate>Tue, 8 Aug 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/anton-mirhorodchenko</guid>
    </item>
    <item>
      <title>Secure cloud deployment and delivery</title>
      <link>https://github.com/readme/guides/github-actions-eli-lilly</link>
      <description>Pharmaceutical giant Eli Lilly shows how they used GitHub to build a better developer environment and increase speed to delivery.</description>
      <pubDate>Tue, 11 Jul 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/github-actions-eli-lilly</guid>
    </item>
    <item>
      <title>Make your first open source contribution in four easy steps</title>
      <link>https://github.com/readme/guides/first-oss-contribution</link>
      <description>This guide demystifies open source software and provides a comprehensive roadmap for making your first contribution. Enhance your skills, grow your network, and make a real difference in the tech community.</description>
      <pubDate>Tue, 11 Jul 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/first-oss-contribution</guid>
    </item>
    <item>
      <title>Turbulent times call for adaptive leadership</title>
      <link>https://github.com/readme/guides/adaptive-leadership</link>
      <description>Learn what adaptive leadership is, how it compares to other leadership styles, and how you can adopt its principles.
</description>
      <pubDate>Tue, 11 Jul 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/adaptive-leadership</guid>
    </item>
    <item>
      <title>TypeScript and the dawn of gradual types</title>
      <link>https://github.com/readme/featured/typescript-gradual-types</link>
      <description>TypeScript ushered in an era of gradual typing, where developers don’t have to choose between the agility of dynamic languages and the type safety of static languages, all while helping avoid the pitfalls of both.</description>
      <pubDate>Tue, 11 Jul 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/typescript-gradual-types</guid>
    </item>
    <item>
      <title>From fixing computers on farms to democratizing DevOps</title>
      <link>https://github.com/readme/stories/kyler-middleton</link>
      <description>Kyler Middleton’s journey from a small farm in Nebraska to the tech industry is a testament to resilience and empowerment. Read her story of overcoming adversity and democratizing DevOps.</description>
      <pubDate>Tue, 11 Jul 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/kyler-middleton</guid>
    </item>
    <item>
      <title>Finish your projects</title>
      <link>https://github.com/readme/guides/finish-your-projects</link>
      <description>Starting a project can be full of excitement, hope, and blissful productivity. Finishing that last ten percent, however, can feel like too much. Here’s how to get past that and actually finish.</description>
      <pubDate>Tue, 13 Jun 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/finish-your-projects</guid>
    </item>
    <item>
      <title>From chaos to clarity: Use code visibility to illuminate unfamiliar code</title>
      <link>https://github.com/readme/guides/code-visibility-codesee</link>
      <description>What code visibility is, why it matters, and how you can make your code more visible.</description>
      <pubDate>Tue, 13 Jun 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/code-visibility-codesee</guid>
    </item>
    <item>
      <title>Do your part to secure the open source supply chain</title>
      <link>https://github.com/readme/guides/dependency-risk</link>
      <description>Understanding the security risks within the open source ecosystem, from supply chain attacks to protestware, and the tools and methods to mitigate them.</description>
      <pubDate>Tue, 13 Jun 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/guides/dependency-risk</guid>
    </item>
    <item>
      <title>Non-code contributions are the secret to open source success</title>
      <link>https://github.com/readme/featured/open-source-non-code-contributions</link>
      <description>Why non-code contributions like documentation and support are so important to open source, why even experienced programmers should make non-code contributions, and how your project can attract more non-code contributions.</description>
      <pubDate>Tue, 13 Jun 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/open-source-non-code-contributions</guid>
    </item>
    <item>
      <title>Advancing inclusion with progressive enhancement</title>
      <link>https://github.com/readme/stories/aaron-gustafson</link>
      <description>Aaron Gustafson, web standards and accessibility advocate, shares his evolution from early internet user to champion of progressive enhancement—and how we can all work to create a more inclusive digital landscape.</description>
      <pubDate>Tue, 13 Jun 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/aaron-gustafson</guid>
    </item>
    <item>
      <title>How ‘open’ should your open source be?</title>
      <link>https://github.com/readme/featured/how-open-is-open-source</link>
      <description>Open source isn’t one size fits all. Some is open, some closed, and most is in-between. From Litestream to Lua to Prometheus and more, maintainers explain their reasons for where they lie on the spectrum from open to closed, and why there’s more to contributions than code.</description>
      <pubDate>Tue, 9 May 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/how-open-is-open-source</guid>
    </item>
    <item>
      <title> Coding accessibility: Disability as catalyst for creativity</title>
      <link>https://github.com/readme/featured/disability-creativity</link>
      <description>When faced with accessibility barriers, developer Paul Chiou gets creative, building custom hardware interfaces and innovative software solutions for himself and others. Read how Chiou works to increase access for all. </description>
      <pubDate>Tue, 9 May 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/disability-creativity</guid>
    </item>
    <item>
      <title>Champion accessibility to unleash untapped potential</title>
      <link>https://github.com/readme/stories/annalu-waller</link>
      <description>Dr. Annalu Waller, rehabilitation engineer and Professor of Human Communication Technologies at Dundee University, shares her path to overcoming barriers and empowering others to reach their full potential.</description>
      <pubDate>Tue, 9 May 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/annalu-waller</guid>
    </item>
    <item>
      <title>Open source is fueling the future of nuclear physics</title>
      <link>https://github.com/readme/featured/nuclear-fusion-open-source</link>
      <description>A look at the open source artificial intelligence (AI), machine learning (ML), and high performance computing (HPC) tools used in the nuclear fusion ignition breakthrough at Lawerence Livermore Labs.
</description>
      <pubDate>Tue, 11 Apr 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/nuclear-fusion-open-source</guid>
    </item>
    <item>
      <title>Putting the African open source community on the map</title>
      <link>https://github.com/readme/stories/ruth-ikegah</link>
      <description>Once indifferent about computers, Ruth Ikegah put in the time, patience, and work to become a force for change in open source, and is now connecting other Africans with the resources they need to succeed, too.</description>
      <pubDate>Tue, 11 Apr 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/ruth-ikegah</guid>
    </item>
    <item>
      <title>From gaming with your eyes to coding with AI: New frontiers for accessibility</title>
      <link>https://github.com/readme/featured/open-source-accessibility</link>
      <description>Open source offers developers with disabilities the flexibility needed to participate and collaborate. Their contributions and involvement in the research, design, and development of software are integral to making technology accessible to all. </description>
      <pubDate>Tue, 14 Mar 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/featured/open-source-accessibility</guid>
    </item>
    <item>
      <title>Invite the critics and keep learning</title>
      <link>https://github.com/readme/stories/rohan-gupta</link>
      <description>When Windows 11 debuted with limited access, @blueedgetechno created a *very* convincing clone. Hear why he has a female avatar, maintains a growth mindset, and more on The ReadME Project:</description>
      <pubDate>Tue, 14 Mar 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/rohan-gupta</guid>
    </item>
    <item>
      <title>Out of the slums and into open source</title>
      <link>https://github.com/readme/stories/santosh-yadav</link>
      <description>From a slum in India to a Google Developer Expert in Germany, @SantoshYadavDev shares how he leveraged software development as a path out of poverty in The ReadME Project:</description>
      <pubDate>Tue, 14 Feb 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/santosh-yadav</guid>
    </item>
    <item>
      <title>Raising the bar for open source standards</title>
      <link>https://github.com/readme/stories/leonardo-javier-russo</link>
      <description>After seeing first-hand how stifling inaccessibility is, Leonardo strives to create an open source world where everyone can seamlessly participate. He shares his full story on The ReadME Project:</description>
      <pubDate>Tue, 17 Jan 2023 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/leonardo-javier-russo</guid>
    </item>
    <item>
      <title>Building super fans through genuine human connections</title>
      <link>https://github.com/readme/stories/jana-iris</link>
      <description>She never considered tech as a potential career path, but @janaboruta leveraged her empathy to successfully build open source communities of super fans. Her full story, now on The ReadME Project: </description>
      <pubDate>Tue, 13 Dec 2022 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/jana-iris</guid>
    </item>
    <item>
      <title>The purest form of collaboration</title>
      <link>https://github.com/readme/stories/avi-press</link>
      <description>Fueled by the versatility of computer science, @avi_press learned by doing, then started a company to help clear the roadblocks he ran into. Get his full story on The ReadME Project:</description>
      <pubDate>Tue, 15 Nov 2022 02:00:00 +0000</pubDate>
      <guid>https://github.com/readme/stories/avi-press</guid>
    </item>
  </channel>
</rss>Monday                   311 commits         █░░░░░░░░░░░░░░░░░░░░░░░░   04.30 % 
Tuesday                  884 commits         ███░░░░░░░░░░░░░░░░░░░░░░   12.21 % 
Wednesday                1849 commits        ██████░░░░░░░░░░░░░░░░░░░   25.55 % 
Thursday                 1656 commits        ██████░░░░░░░░░░░░░░░░░░░   22.88 % 
Friday                   1215 commits        ████░░░░░░░░░░░░░░░░░░░░░   16.79 % 
Saturday                 1035 commits        ████░░░░░░░░░░░░░░░░░░░░░   14.30 % 
Sunday                   288 commits         █░░░░░░░░░░░░░░░░░░░░░░░░   03.98 % 🕑︎ Time Zone: Asia/Kolkata

💬 Programming Languages: 
TypeScript               14 hrs 2 mins       ██████████░░░░░░░░░░░░░░░   41.18 % 
JSON                     7 hrs               █████░░░░░░░░░░░░░░░░░░░░   20.56 % 
JavaScript               5 hrs 22 mins       ████░░░░░░░░░░░░░░░░░░░░░   15.74 % 
Bash                     4 hrs 7 mins        ███░░░░░░░░░░░░░░░░░░░░░░   12.10 % 
Other                    2 hrs 19 mins       ██░░░░░░░░░░░░░░░░░░░░░░░   06.84 % 

🔥 Editors: 
VS Code                  24 hrs 17 mins      ██████████████████░░░░░░░   71.27 % 
Cursor                   9 hrs 47 mins       ███████░░░░░░░░░░░░░░░░░░   28.73 % 

💻 Operating System: 
Windows                  34 hrs 5 mins       █████████████████████████   100.00 % # Directrices de la comunidad de GitHub

Millones de desarrolladores de todo el mundo alojan millones de proyectos, tanto de código abierto como cerrado, en GitHub. Somos afortunados de poder desempeñar un papel en permitir la colaboración entre la comunidad de desarrolladores todos los días, lo cual es una responsabilidad que no tomamos a la ligera. Juntos, todos tenemos la emocionante oportunidad de hacer de esta una comunidad de la que podamos estar orgullosos.

Nuestra diversa base de usuarios aporta diferentes perspectivas, ideas y experiencias, y abarca desde personas que crearon su primer proyecto "Hello World" la semana pasada hasta los desarrolladores de software más conocidos del mundo. Estamos comprometidos a hacer de GitHub un entorno que acoja todas las diferentes voces y perspectivas que nuestra comunidad tiene para ofrecer, mientras mantenemos un lugar seguro para que los desarrolladores hagan su mejor trabajo.

Al describir cómo consideramos que debe ser una [comunidad segura, acogedora y productiva](https://opensource.guide/building-community/) en GitHub, esperamos ayudarlo a comprender la mejor manera de interactuar y colaborar en nuestra plataforma, de conformidad con los [Términos de servicio de GitHub](/es/site-policy/github-terms/github-terms-of-service) y con las [Directivas de Uso Aceptable de GitHub](/es/site-policy/acceptable-use-policies/github-acceptable-use-policies).

Alentamos a los miembros de nuestra comunidad a comunicar las expectativas con claridad, [moderar](#what-if-something-or-someone-offends-you) sus proyectos siempre que sea posible y [denunciar](https://github.com/contact/report-abuse) cualquier contenido que infrinja nuestras [directivas](/es/site-policy/github-terms/github-terms-of-service). El personal de GitHub investigará cualquier informe de abuso y puede moderar el contenido público en nuestro sitio que determinemos que viola nuestros Términos de servicio.

## Mantener una comunidad fuerte

El objetivo principal de la comunidad de GitHub es colaborar en proyectos de software. Estamos comprometidos a mantener una comunidad en la que los usuarios sean libres de expresarse y desafiar las ideas de los demás, tanto técnicas como de otro tipo. Al mismo tiempo, es importante que los usuarios sigan siendo respetuosos y dejen espacio para que otros contribuyan abiertamente. Con el fin de fomentar un entorno seguro y productivo, alentamos a los miembros de nuestra comunidad a consultar estas pautas para informarse sobre cómo interactúan en nuestra plataforma. A continuación, encontrará algunas sugerencias sobre cómo tener interacciones exitosas como miembro valioso de la comunidad de GitHub.

* **Sea acogedor y tenga una actitud abierta**. A nuestra comunidad se incorporan nuevos usuarios todos los días. Algunos son desarrolladores bien establecidos, mientras que otros recién comienzan. Esté abierto a otras ideas y niveles de experiencia. Deja espacio para opiniones distintas a las tuyas y da la bienvenida a los nuevos colaboradores y a los que recién comienzan.

* **Sea respetuoso**. Trabajar en un entorno de colaboración trae consigo la posibilidad de que surjan desacuerdos. Pero recuerda criticar las ideas, no las personas. Comparta críticas reflexivas y constructivas y sea cortés con las personas con las que interactúa. Si no puede participar de manera respetuosa, considere dar un paso atrás o usar algunas de nuestras herramientas de moderación para reducir una situación tensa.

* **Sea empático**. GitHub es una comunidad global compuesta por personas de muy diversas procedencias y perspectivas, que pueden no ser iguales a las suyas. Trate de ponerse en el lugar de los demás y comprenda sus sentimientos antes de dirigirse a ellos. Haz tu mejor esfuerzo para ayudar a hacer de GitHub una comunidad donde otros se sientan seguros para hacer contribuciones, participar en debates y compartir diferentes ideas.

## ¿Qué pasa si algo o alguien te ofende?

Si bien algunos desacuerdos se pueden resolver con una comunicación directa y respetuosa entre los miembros de la comunidad, entendemos que no siempre es así. Animamos a nuestra comunidad a ponerse en contacto con el soporte técnico de GitHub a través del [Portal de soporte técnico de GitHub](https://support.github.com/) cuando creen que el contenido o la actividad que han encontrado infringen nuestras directivas. Sin embargo, si te encuentras con algo o alguien en el sitio que encuentras objetable, aquí hay algunas formas en que GitHub te permite tomar medidas:

* **Comunique sus expectativas**. Los responsables del mantenimiento pueden establecer pautas específicas de la comunidad para ayudar a los usuarios a entender cómo interactuar con sus proyecto; por ejemplo, en el archivo LÉAME de un repositorio, en un [archivo de contribución](/es/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors), o en un [código de conducta específico](/es/communities/setting-up-your-project-for-healthy-contributions/adding-a-code-of-conduct-to-your-project). Puede encontrar más información sobre el desarrollo de comunidades en la página [Comunidades](/es/communities).

* **Modere los comentarios**. Los usuarios con [privilegios de acceso de escritura](/es/organizations/managing-user-access-to-your-organizations-repositories/repository-roles-for-an-organization) en un repositorio pueden [editar, eliminar y ocultar los comentarios de cualquier persona](/es/communities/moderating-comments-and-conversations/managing-disruptive-comments) sobre las confirmaciones, las solicitudes de incorporación de cambios y las ediciones. Cualquier persona con acceso de lectura a un repositorio puede ver el historial de edición de un comentario. Los autores de los comentarios y las personas con acceso de escritura a un repositorio también pueden eliminar información confidencial del [historial de edición de un comentario](/es/communities/moderating-comments-and-conversations/tracking-changes-in-a-comment). Moderar los proyectos puede parecer una tarea abrumadora si hay mucha actividad, pero puede [añadir colaboradores](/es/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-personal-account-settings/permission-levels-for-a-personal-account-repository#collaborator-access-for-a-repository-owned-by-a-personal-account) que lo ayuden a gestionar la comunidad.

* **Bloquee la conversación** . Si un debate en una edición, una solicitud de incorporación de cambios o una confirmación no se consigue controlar, se desvía del tema o infringe el código de conducta del proyecto o las directivas de GitHub, los propietarios, colaboradores y cualquier otra persona con acceso de escritura puede establecer un bloqueo temporal o permanente en la conversación. Para más información, consulta [Bloquear conversaciones](/es/communities/moderating-comments-and-conversations/locking-conversations).

* **Bloquee al usuario** . Si hay un usuario determinado con el que prefiere no interactuar, puede [bloquearlo para su cuenta personal](/es/communities/maintaining-your-safety-on-github/blocking-a-user-from-your-personal-account) o [para su organización](/es/communities/maintaining-your-safety-on-github/blocking-a-user-from-your-organization).

* **Limite las interacciones**. Si su proyecto público está recibiendo atención no deseada, es objeto de troleo, correo no deseado o cualquier otra actividad no deseada, tiene la opción de establecer [límites de interacción temporales](/es/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository) para evitar que determinados usuarios interactúen con su repositorio. Incluso puede establecer [límites de revisión del código](https://github.blog/2021-11-01-github-keeps-getting-better-for-open-source-maintainers/#preventing-drive-by-pull-request-approvals-and-requested-changes) para asegurarse de que las contribuciones a sus proyectos sean de calidad.

Si bien nos apasiona capacitar a los responsables del mantenimiento para que moderen sus propios proyectos, póngase en contacto con nosotros en con nosotros a través del [Soporte técnico de GitHub](https://support.github.com) si necesita apoyo adicional para hacer frente a una situación.

## ¿Qué sucede si alguien viola las políticas de GitHub?

Confiamos en los informes de la comunidad, así como en la detección proactiva, para ayudar a garantizar que GitHub sea una plataforma segura, acogedora y productiva para los desarrolladores de software. Hay una variedad de factores que consideramos cuando nos enteramos de un comportamiento o contenido que no está en línea con las políticas de GitHub. Sin embargo, nuestro enfoque de aplicación de políticas y moderación de contenido prioriza nuestra visión de ser el hogar de todos los desarrolladores. Esto significa:

* Optimizamos para la colaboración de código. Reconocemos que el código puede tener múltiples usos y distinguimos entre cómo se usa el código en la plataforma y otros posibles usos. También pensamos en cómo nuestras acciones de cumplimiento pueden afectar una red de interdependencias potencialmente complicada en toda la plataforma y nuestro objetivo es restringir la menor cantidad posible de contenido legítimo.

* Adoptamos un enfoque centrado en el ser humano para la moderación de contenido y adaptamos nuestras respuestas para satisfacer las necesidades de una situación específica. Nuestro equipo global investiga los informes que recibimos caso por caso, teniendo en cuenta el contexto y los hechos circundantes, antes de tomar medidas. Esto podría incluir tener en cuenta el contenido potencialmente ofensivo que se publica de una manera que carece de contexto o facilita que otros usuarios vean o interactúen sin saberlo mientras usan GitHub. En esos casos, podemos favorecer la moderación para salvaguardar nuestra comunidad.

* Nuestras decisiones se basan en nuestra creencia fundamental de que servir a una comunidad interconectada y potenciar el progreso humano a través de la colaboración de los desarrolladores requiere un compromiso con la diversidad, la inclusión y la pertenencia.

Cuando hayamos decidido que se justifica una acción de moderación, estas son algunas de las formas en que podemos responder:

* Eliminación del contenido ofensivo
* Bloquear o deshabilitar el contenido ofensivo
* Rebajar la visibilidad del contenido ofensivo
* Ocultar una cuenta de usuario u organización de la vista pública
* Suspender una cuenta de usuario u organización

## Apelación y Restablecimiento

Si su contenido o su cuenta se han deshabilitado o restringido y desea restablecerlos o presentar una apelación, consulte la [página Apelación y Restablecimiento de GitHub](/es/site-policy/acceptable-use-policies/github-appeal-and-reinstatement) para obtener información sobre el proceso y utilice nuestro [formulario de apelación y restablecimiento](https://support.github.com/contact/reinstatement) para enviar una solicitud al respecto.

## Avisos legales

Dedicamos estas Pautas de la Comunidad de GitHub al dominio público para que cualquiera las pueda usar, reutilizar, adaptar o realizar cualquier otra acción con ellas, en virtud de la licencia [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/).

Estas son solo unas pautas, que no modifican los [Términos de servicio de GitHub](/es/site-policy/github-terms/github-terms-of-service) ni pretenden ser una lista exhaustiva. En virtud de esos términos, GitHub conserva la plena discreción para eliminar cualquier contenido o resolver cualquier cuenta si incurren en cualquier actividad que infrinja las [Directivas de Uso Aceptable de GitHub](/es/site-policy/acceptable-use-policies/github-acceptable-use-policies). Estas pautas describen cuándo ejerceremos esa discreción.https://docs.github.com/es/site-policy/github-terms/github-community-guidelinesSkip to main content


Microsoft

Xbox
Home

Games & apps
Back up your game captures
Note Some features may not be available in all regions.
Game clips and screenshots that are uploaded to the Xbox network may be deleted after 90 days. Be sure to back up the captures that you want to keep indefinitely.
Note that while captures that are backed up on an external drive can’t be uploaded to the Xbox network from your console, they can be easily uploaded to OneDrive.
Watch this video to learn how to back up your game clips:
Video instructions
Ways to back up your captures

Back up your captures on your Xbox console

Back up by uploading to OneDrive
To bulk delete, move, or manage where you store your game clips or screenshots on your Xbox console, launch the Captures app:
Press the Xbox button  to open the guide.
Go to My games & apps > See all > Apps > Captures.
Set your filters to locate the captures you want to back up.
Select Manage.
When you select one or more captures, you’ll see a list of backup options. To back up the captures you’ve selected, choose Upload to OneDrive.
This option adds the selected captures to your OneDrive account but does not delete them from the console or the Xbox network.
You can manually select captures to upload to OneDrive, or choose Select all to move them all at once. After the upload is complete, it’s a good idea to check your OneDrive folder to confirm that your captures were uploaded.
To do so, sign in to OneDrive.com with your Microsoft account and go to the My Files > Pictures or Videos tab to find your captures. Screenshots will appear in Pictures, while game clips will appear in Videos. Note that your captures will be in the subfolder labeled Xbox Screenshots under Pictures and Xbox Game DVR under Videos. You can rename these folders if you’d like.
You also have the option to have your future captures automatically uploaded to OneDrive. To do so, press the Xbox button  and go to Profile & system > Settings > Preferences > Capture & share > Automatic uploads > To OneDrive.
All Microsoft accounts have up to 5 gigabytes of storage on OneDrive. If you need more storage, consider subscribing to a Microsoft 365 plan.
Microsoft 365
Issues backing up to OneDrive
If you experience issues while backing up to OneDrive, try the following steps to back up your captures:
Check that your OneDrive isn't full.
If you are trying to upload a large group of files, try smaller batches.
Make sure your network connection speeds are above the recommended minimum standard. For more info, see Step 2 in "Troubleshoot your network connection speed".
Check the Xbox status page.
Try your upload again later.
Troubleshoot your network connection speed
Xbox status page

Back up by copying to external storage
Launch the Captures app:
Press the Xbox button  to open the guide.
Go to My games & apps > See all > Apps > Captures.
Set your filters to locate the captures you want to back up.
Select Manage.
When you select one or more captures, you’ll see a list of backup options. To back up the captures you’ve selected, choose Copy to external storage.
This option copies the selected captures to your external storage but does not delete them from the console or the Xbox network.
You can manually select captures to copy to external storage, or choose Select all to copy them all at once.
Note that the USB drive you use must be formatted as NTFS. You can’t use the same drive that your games are installed on, which is formatted differently. For more info about setting up an external storage device, visit:
Manage storage on your Xbox console
You have the option to have your future captures automatically saved directly to an external drive. To do so, press the Xbox button  and go to Profile & system > Settings > Preferences > Capture & share > Capture save location > Name of external drive you use for captures.

Back up your captures on your Windows PC
PC captures are unable to be uploaded to the Xbox network and therefore are not subject to the 90-day deletion policy. However, you can back them up by following the steps below. To locate and back up your captures:
Press the Windows logo key  + G on your PC to open Game Bar.
In the Widgets menu, select Gallery.
Select a capture and then select Open file location. This will open the Captures folder on your C: drive.
From here, you can move your local files to OneDrive or another storage location.
After the upload is complete, it’s a good idea to check your OneDrive folder to confirm that your captures were uploaded. To do so, sign in to OneDrive.com with your Microsoft account and go to the Photos tab to find your captures.
To learn more about storage management, visit:
Free up drive space in Windows
Manage files and folders in OneDrive
Get the OneDrive app for Windows

Back up your captures by saving to a mobile device
Note If you have captures you want to back up, and you don’t have a console, you’ll need to back up your clips to your mobile device through the Xbox mobile app. The Xbox app is available through the Apple App Store or the Google Play Store.
To back up your captures to your mobile device:
Open the Xbox mobile app.
Go to My Library .
Select a capture you wish to save and click Save.

Related topics
Capture game clips and screenshots
Troubleshoot recording game clips on Xbox
Share game clips and screenshots
Still need help?
Chat with our support virtual agent.

Get fast automated support, 24/7
Get accessibility help
Accessible help and resources to get your Xbox questions answered.

Disability answer desk
Get accessibility help
Customer support
Contact us
Xbox status
Your Microsoft account
Microsoft accessibility conformance report
Resources
Xbox News
Feedback
Community Standards
Photosensitive seizure warning
Product safety
For developers
Games
ID@Xbox
Windows
Creators Program
Designed for Xbox
United States - English
Your Privacy Choices
Consumer Health Privacy
Sitemap
Privacy
Terms of use
Trademarks
Safety & eco
About our ads
© Microsoft 2026package.jsonhttps://mtmanagerapk.app/m-lisenseMicrosoftCopilot 

Iniciar sesión en tu cuenta
Preguntas más frecuentes sobre Copilot en suscripciones de Microsoft 365
Se aplica a
Microsoft 365 Copilot está disponible en los planes personal, familiar y premium de Microsoft 365. Es posible que tenga preguntas sobre cómo usar y administrar Copilot en su suscripción de Microsoft 365. En cada sección siguiente, seleccione una pregunta para expandirla y obtener más información.  

Acerca de Microsoft Copilot
Microsoft Copilot es un asistente digital con tecnología de IA diseñado para ayudarle con una variedad de tareas y actividades. Puede crear borradores de contenido, recomendar diferentes formas de volver a redactar algo que ha escrito, sugerir e insertar imágenes o pancartas, crear presentaciones de PowerPoint desde sus documentos de Word y muchas otras cosas útiles.

Para obtener información sobre cómo usar Copilot en Microsoft 365 aplicaciones, elija cualquiera de las siguientes preguntas y expándala para obtener más información. 

¿Para qué escenarios comunes puede alguien usar Copilot en Microsoft 365?
Copilot aporta el poder de la IA a las aplicaciones de Microsoft 365 que usa todos los días para dar rienda suelta a su creatividad, liberar su potencial y ayudarle a comunicarse con confianza. Con Copilot, puede planear fácilmente su próximo viaje o evento con OneNote, perfeccionar su currículum vítae y carta de presentación en Word, escribir rápidamente correos electrónicos excelentes con el tono adecuado y ponerse al día con largas conversaciones de correo electrónico en Outlook, o producir una presentación de PowerPoint para su siguiente discurso de cliente. Copilot trabaja junto a usted, cuidando el trabajo ocupado para que pueda mejorar su flujo de trabajo y hacer tiempo para cosas que le den alegría. 

¿Funciona Copilot en todas mis aplicaciones (por ejemplo, outlook para Word, Word en PowerPoint, etc.)?
Actualmente existen varios tipos de funcionalidades, incluida la posibilidad de hacer referencia a un archivo para iniciar un documento o una presentación en Word y PowerPoint, respectivamente, así como la capacidad de generar una imagen con Designer directamente desde los lienzos de Word o PowerPoint desde los paneles de chat Copilot. 

Importante: Si no ve Copilot en las aplicaciones de Microsoft 365, obtenga información sobre cómo actualizar la licencia.

¿Cuál es la diferencia entre la aplicación móvil de Copilot y la experiencia de Copilot en las aplicaciones de Microsoft 365?
La aplicación móvil Copilot es una experiencia de chat conversacional. Microsoft 365 Copilot lleva Copilot a aplicaciones como Word, PowerPoint, Excel y Outlook.

Importante: Los límites de edad mínima pueden aplicarse a la activación y el uso de suscripciones de características de IA.

Nota:  Copilot en Excel requiere que Autoguardado esté habilitado, lo que significa que el archivo debe guardarse en OneDrive; no funciona con archivos no guardados.

Administración de suscripciones de Microsoft 365
Para obtener información sobre cómo administrar tu suscripción de Microsoft 365 con Copilot, elige cualquiera de las siguientes preguntas y expándala para obtener más información. 

¿Cómo puedo administrar mi suscripción de Microsoft 365 Personal, Familia o Premium?
Puede administrar su suscripción de Microsoft 365 iniciando sesión en su cuenta o viendo el panel de su cuenta si ya ha iniciado sesión. Obtenga más información sobre cómo administrar las suscripciones. ​​​​​​​

Soy un Microsoft 365 Familia o suscriptor premium. ¿Puedo compartir el acceso a Copilot como parte de mi plan?
Las características de IA de Word, Excel, PowerPoint, Outlook y Designer incluidas en Microsoft 365 planes Familia y Premium solo están disponibles para el propietario de la suscripción y no se pueden compartir con otros usuarios.

Nota:  Copilot en Excel requiere que Autoguardado esté habilitado, lo que significa que el archivo debe guardarse en OneDrive; no funciona con archivos no guardados.

¿Hay ofertas especiales para estudiantes universitarios?
Sí, el mejor valor para los estudiantes universitarios es nuestra versión con descuento de Microsoft 365 Premium, que proporciona acceso a nuestras potentes aplicaciones de productividad y creatividad, ahora fusionadas con IA en Word, Excel, PowerPoint, Designer y Outlook, junto con un amplio almacenamiento en la nube y seguridad digital avanzada. Obtenga más información sobre nuestras ofertas para estudiantes.

Nota: Copilot en Excel requiere que Autoguardado esté habilitado, lo que significa que el archivo debe guardarse en OneDrive; no funciona con archivos no guardados.

He tenido noticias sobre cambios en los planes de Microsoft 365, pero no he recibido ningún correo electrónico.  
Como suscriptor existente, no verás un cambio con el precio de la suscripción hasta la próxima renovación. Recibirá un aviso por correo electrónico con al menos 30 días de antelación a la fecha de renovación. Las fechas de renovación para algunos suscriptores anuales se extienden hasta enero de 2026, por lo que es posible que no reciba un aviso por correo electrónico hasta diciembre de 2025. 

Créditos de IA
Microsoft 365 Personal, familia y planes Premium ahora incluyen créditos de IA. Para obtener información sobre los créditos de IA y cómo usarlos con tu suscripción, consulta Descripción de los créditos de IA. 

¿Dónde están mis potenciadores en Designer?
En Designer, todas las imágenes ahora se mejoran automáticamente. Esto significa que la velocidad de creación ya no variará en función de la frecuencia de creación. Todas las imágenes se crean a la velocidad más rápida disponible.

¿Por qué no veo Copilot en mis aplicaciones, aunque debería ser apto para créditos de IA?  
Como suscriptor de Microsoft 365 Personal, familia o Premium, tiene acceso a créditos de IA que se pueden usar para acceder a las características de IA en Word, Excel, PowerPoint, Outlook, Forms, OneNote, Designer, Bloc de notas, Fotos y Paint.  

El uso de características de IA en estas aplicaciones se limita a las personas que cumplen ciertos requisitos de edad, que pueden variar según la región. Los usuarios que no cumplan estos requisitos de edad para su región no podrán usar las características de IA, incluso si cumplen los requisitos para los créditos de IA. En la mayoría de los casos, las características de IA se quitarán de las aplicaciones de Microsoft 365 afectadas. 

Privacidad
Para obtener más información sobre los límites de privacidad y edad para IA, elige cualquiera de las siguientes preguntas y expándala para obtener más información.

Copilot en aplicaciones de Microsoft 365 disponibles en suscripciones de Microsoft 365 Personal, Familia y Premium está cubierto por el Contrato de servicios de Microsoft y los Términos de uso de Copilot. Para obtener información sobre cómo Microsoft usa sus datos personales, consulte la Declaración de privacidad de Microsoft.

¿Dónde puedo obtener más información sobre la privacidad de mis datos con Copilot en las aplicaciones de Microsoft 365?
Copilot y Microsoft 365 se basan en el enfoque completo de Microsoft para la seguridad, el cumplimiento y la privacidad. Para obtener más información sobre la privacidad, vea Copilot en aplicaciones de Microsoft 365 para el hogar: sus datos y privacidad.

Cómo desactivar Copilot?
Sabemos que hay ocasiones en las que no se desea usar Copilot, por lo que hemos agregado la configuración en aplicaciones como Word, Excel y PowerPoint que le permiten desactivar o activar Copilot según sea necesario. Para obtener más información, vea Cómo desactivar Copilot en suscripciones de Microsoft 365 Familia y Personal.

Nota: No puede desactivar las características de Copilot en Designer, Bloc de notas o Paint.

Tengo una cuenta profesional y una cuenta personal vinculadas. ¿Copilot puede obtener acceso a mis archivos de trabajo? 
Si su empresa tiene activado el acceso a varias cuentas, puede usar su suscripción personal de Copilot en el trabajo. Tenga en cuenta que todos los permisos y acceso permanecen vinculados a su cuenta profesional. Para obtener más información, consulta Usar Microsoft 365 Personal, Familia o Premium en el trabajo. 

¿Hay límites de edad en el uso de las aplicaciones y características de IA?   
Sí. Las características de IA de las aplicaciones de Microsoft 365 (Word, Excel, PowerPoint, Outlook y OneNote) están deshabilitadas para los usuarios menores de las edades que se enumeran aquí. Para obtener información sobre las restricciones de edad en otras aplicaciones y características de Microsoft Copilot, vea ¿Qué antigüedad tengo que tener para usar Copilot?

¿Qué controles como padre tengo sobre el acceso de mi hijo a las características de IA generativa?   
La mayoría de las aplicaciones que proporcionan acceso a créditos de IA restringen automáticamente el acceso a IA en función de los requisitos de edad. Para asegurarse de que esta protección está funcionando, compruebe que la edad está correctamente establecida para la cuenta de su hijo. Consulte Cómo cambiar la fecha de nacimiento en una cuenta de Microsoft para más información. 

Algunas aplicaciones de Windows, como Paint y el Bloc de notas, pueden seguir usando créditos de IA. Los padres que deseen limitar el acceso a la IA en estas aplicaciones pueden aprovechar los controles de Windows Family Safety.

¿Necesita más ayuda?
¿Cómo podemos ayudarte?

¿Quiere más opciones?
Descubrir
Comunidad
Póngase en contacto con nosotros
Explore las ventajas de las suscripciones, examine los cursos de aprendizaje, aprenda a proteger su dispositivo y mucho más.



Ventajas de la suscripción de Microsoft 365



Aprendizaje de Microsoft 365



Seguridad de Microsoft



Centro de accesibilidad

¿Le ha sido útil esta información? Sí No
Novedades
Surface Pro
Surface Laptop
Surface Laptop Studio 2
Copilot para organizaciones
Copilot para uso personal
Microsoft 365
Explora los productos de Microsoft
Aplicaciones de Windows 11
Microsoft Store
Perfil de la cuenta
Centro de descarga
Soporte de Microsoft Store
Devoluciones
Seguimiento de pedidos
Reciclar
Garantías comerciales
Educación
Microsoft Educación
Dispositivos para educación
Microsoft Teams para Educación
Microsoft 365 Educación
Office Educación
Formación y desarrollo de educadores
Ofertas para estudiantes y padres
Azure para estudiantes
Empresas
Microsoft AI
Seguridad de Microsoft
Azure
Dynamics 365
Microsoft 365
Microsoft 365 Copilot
Microsoft Teams
Pequeñas empresas
Desarrolladores y TI
Desarrollador de Microsoft
Microsoft Learn
Soporte técnico para aplicaciones del marketplace de IA
Microsoft Tech Community
Microsoft Marketplace
Microsoft Power Platform
Marketplace Rewards
Visual Studio
Compañía
Oportunidades de empleo
Acerca de Microsoft
Noticias de la compañía
Privacidad en Microsoft
Inversores
Sostenibilidad
Español (España, alfabetización internacional)
Tus opciones de privacidad
Privacidad de la salud del consumidor
Ponte en contacto con Microsoft Privacidad Condiciones de uso Marcas registradas Sobre nuestra publicidad Docs de cumplimiento de la UE Informes regulatorios © Microsoft 2026Ir al contenido principal


Microsoft

ME
Xbox
Inicio

Juegos y aplicaciones
¿Qué juegos son compatibles con mi consola Xbox?
Juega miles de juegos de cuatro generaciones de Xbox, que incluyen los títulos optimizados para Xbox Series X|S.
Jugar a juegos en todas las consolas Xbox

Jugar juegos en Xbox Series X|S
La mayoría de los juegos de Microsoft Store pueden jugarse en Xbox Series X|S. Los títulos que aparecen como Optimizado para Xbox Series X|S se crean desde cero (o se vuelven a crear) para usar la potencia de la consola Xbox Series X|S. Para ver la lista completa de los títulos que admiten Optimizado para Xbox Series X|S, consulta:
Optimizado para Xbox Series X|S

Utilizar juegos de Xbox One en Xbox Series X|S
La mayoría de los juegos de Xbox One pueden reproducirse en Xbox Series X|S. Además, los juegos pueden tener una mejor apariencia y rendimiento, y algunos títulos ofrecen velocidades de fotograma más rápidas, HDR automático y una resolución de pantalla mejorada.
Aspectos que debes tener en cuenta
Un pequeño número de títulos que se pueden jugar en Xbox One no son compatibles con Xbox Series X|S. Para obtener más información, consulta la sección "Títulos excluidos" que encontrarás abajo.
La compatibilidad de los juegos Xbox Series X|S con la consola Xbox One se proporciona de manera individual de acuerdo con el desarrollador de cada juego. Si no estás seguro de qué consola es compatible con tu juego, revisa la caja o la página de detalles del juego en Microsoft Store.
Debido a que Xbox Series S es una consola totalmente digital, los juegos basados en un disco no son compatibles con esta.

Jugar juegos de Xbox mediante el juego en la nube
Con una suscripción a Xbox Game Pass, puedes hacer streaming de una amplia selección de juegos que se pueden jugar en la nube en dispositivos compatibles, sin necesidad de usar una consola. Esto incluye muchos títulos compatibles con versiones anteriores. Para ver qué juegos están disponibles, visita:
Cloud Gaming con Game Pass
Para obtener más información sobre los juegos en la nube y sus requisitos, visita:
Cómo usar juegos en la nube

Jugar Xbox 360 y los juegos originales de Xbox en Xbox One o Xbox Series X|S
Los juegos de Xbox 360 y de Xbox original que son compatibles con Xbox One también pueden jugarse en Xbox Series X|S. Consulta la lista completa de juegos compatibles con versiones anteriores aquí:
Biblioteca de juegos compatibles con versiones anteriores
Nota Algunos juegos compatibles con versiones anteriores ya no están disponibles para su venta. Si compraste previamente un juego compatible con versiones anteriores en Xbox 360 o tienes un disco de juego, puedes jugarlo en la consola Xbox One o Xbox Series X|S. Solo las compras digitales funcionarán en Xbox One S All Digital Edition y Xbox Series S. Además, es posible que algunos juegos o contenido descargable no estén disponibles en todas las regiones.

Utilizar juegos de Xbox original en Xbox 360
Ve la lista completa de los juegos de Xbox original que se pueden jugar en Xbox 360 aquí:
Disfrutar de juegos de Xbox original en una consola Xbox 360
Nota La mayoría de los juegos de Xbox original compatibles con versiones anteriores se pueden jugar en Xbox 360, Xbox One y Xbox Series X|S. Sin embargo, algunos juegos de Xbox original compatibles con versiones anteriores solo están disponibles en las consolas Xbox One y Xbox Series X|S y no se reproducen en Xbox 360.

Títulos excluidos

Juegos que requieren el sensor Kinect
Xbox Series X|S no es compatible con el sensor Kinect. Los siguientes juegos que necesitan Kinect no son compatibles con Xbox Series X|S:
Título	Editor
Kinect Sports Rivals
Microsoft Studios
Dance Central Spotlight
Microsoft
Fruit Ninja Kinect 2
Halfbrick Studios
Shape Up
Ubisoft
Xbox Fitness
Microsoft Studios
Just Dance 2014
Ubisoft
Rabbids Invasión: El programa de televisión interactivo
Ubisoft
Zumba Fitness World Party
Majesco Entertainment
Kung-Fu para Kinect
Virtual Air Guitar Company
Squid Hero
Virtual Air Guitar Company
Beatsplosion
Virtual Air Guitar Company
Boom Ball
Virtual Air Guitar Company
Fighter Within
Ubisoft
Boom Ball 2
Virtual Air Guitar Company
Just Dance Disney Party 2
Ubisoft
Disney Fantasia: Music Evolved
Disney Interactive
Boom Ball 3 for Kinect
Virtual Air Guitar Company
FRU
Through Games
Air Guitar Warrior para Kinect
Virtual Air Guitar Company
Slice Zombies para Kinect
MADE GmbH
"ZAZEN"; juego de meditación zen
Nangok Software
Commander Cherry para Kinect
Grandé Games
Perfect Woman
Peter Lu & Lea Schönfelder

Aplicaciones
Algunas aplicaciones no son compatibles con la serie Xbox X | S. Entre otros:
EA Play Hub
Importante Para tener acceso al contenido de la reproducción de EA, ve a Mis juegos & aplicaciones > Biblioteca completa > EA Play.
OneGuide

Temas relacionados
Biblioteca de juegos compatibles con versiones anteriores
¿Qué accesorios son compatibles con Xbox Series X|S?
Buscar tus juegos y complementos
¿Todavía necesitas ayuda?
Chatea con nuestro agente virtual de atención al cliente.

Obtén soporte automatizado rápido, 24/7
Obtener ayuda de accesibilidad
Ayuda y recursos accesibles para obtener respuestas a tus preguntas sobre Xbox.

Answer Desk Accesibilidad
Obtener ayuda de accesibilidad
Atención al cliente
Ponte en contacto con nosotros
Estado de Xbox
Tu cuenta Microsoft
Informe de conformidad de accesibilidad
Recursos
Noticias de Xbox
Comentarios
Estándares de la comunidad
Advertencia sobre ataques fotosensibles
Seguridad del producto
Para desarrolladores
Juegos
ID@Xbox
Windows
Creators Program
México - Español
Tus opciones de privacidad
Privacidad de salud del consumidor
Privacidad
Aviso legal
Marcas Registradas
Sobre nuestra publicidad
© Microsoft 2026
		Git installation

Normally you can just do "make" followed by "make install", and that
will install the git programs in your own ~/bin/ directory.  If you want
to do a global install, you can do

	$ make prefix=/usr all doc info ;# as yourself
	# make prefix=/usr install install-doc install-html install-info ;# as root

(or prefix=/usr/local, of course).  Just like any program suite
that uses $prefix, the built results have some paths encoded,
which are derived from $prefix, so "make all; make prefix=/usr
install" would not work.

The beginning of the Makefile documents many variables that affect the way
git is built.  You can override them either from the command line, or in a
config.mak file.

Alternatively you can use autoconf generated ./configure script to
set up install paths (via config.mak.autogen), so you can write instead

	$ make configure ;# as yourself
	$ ./configure --prefix=/usr ;# as yourself
	$ make all doc ;# as yourself
	# make install install-doc install-html;# as root

If you're willing to trade off (much) longer build time for a later
faster git you can also do a profile feedback build with

	$ make prefix=/usr profile
	# make prefix=/usr PROFILE=BUILD install

This will run the complete test suite as training workload and then
rebuild git with the generated profile feedback. This results in a git
which is a few percent faster on CPU intensive workloads.  This
may be a good tradeoff for distribution packagers.

Alternatively you can run profile feedback only with the git benchmark
suite. This runs significantly faster than the full test suite, but
has less coverage:

	$ make prefix=/usr profile-fast
	# make prefix=/usr PROFILE=BUILD install

Or if you just want to install a profile-optimized version of git into
your home directory, you could run:

	$ make profile-install

or
	$ make profile-fast-install

As a caveat: a profile-optimized build takes a *lot* longer since the
git tree must be built twice, and in order for the profiling
measurements to work properly, ccache must be disabled and the test
suite has to be run using only a single CPU.  In addition, the profile
feedback build stage currently generates a lot of additional compiler
warnings.

Issues of note:

 - Ancient versions of GNU Interactive Tools (pre-4.9.2) installed a
   program "git", whose name conflicts with this program.  But with
   version 4.9.2, after long hiatus without active maintenance (since
   around 1997), it changed its name to gnuit and the name conflict is no
   longer a problem.

   NOTE: When compiled with backward compatibility option, the GNU
   Interactive Tools package still can install "git", but you can build it
   with --disable-transition option to avoid this.

 - You can use git after building but without installing if you want
   to test drive it.  Simply run git found in bin-wrappers directory
   in the build directory, or prepend that directory to your $PATH.
   This however is less efficient than running an installed git, as
   you always need an extra fork+exec to run any git subcommand.

   It is still possible to use git without installing by setting a few
   environment variables, which was the way this was done
   traditionally.  But using git found in bin-wrappers directory in
   the build directory is far simpler.  As a historical reference, the
   old way went like this:

	GIT_EXEC_PATH=`pwd`
	PATH=`pwd`:$PATH
	GITPERLLIB=`pwd`/perl/build/lib
	export GIT_EXEC_PATH PATH GITPERLLIB

 - By default (unless NO_PERL is provided) Git will ship various perl
   scripts. However, for simplicity it doesn't use the
   ExtUtils::MakeMaker toolchain to decide where to place the perl
   libraries. Depending on the system this can result in the perl
   libraries not being where you'd like them if they're expected to be
   used by things other than Git itself.

   Manually supplying a perllibdir prefix should fix this, if this is
   a problem you care about, e.g.:

       prefix=/usr perllibdir=/usr/$(/usr/bin/perl -MConfig -wle 'print substr $Config{installsitelib}, 1 + length $Config{siteprefixexp}')

   Will result in e.g. perllibdir=/usr/share/perl/5.26.1 on Debian,
   perllibdir=/usr/share/perl5 (which we'd use by default) on CentOS.

 - Unless NO_PERL is provided Git will ship various perl libraries it
   needs. Distributors of Git will usually want to set
   NO_PERL_CPAN_FALLBACKS if NO_PERL is not provided to use their own
   copies of the CPAN modules Git needs.

 - Git is reasonably self-sufficient, but does depend on a few external
   programs and libraries.  Git can be used without most of them by adding
   the appropriate "NO_<LIBRARY>=YesPlease" to the make command line or
   config.mak file.

	- "zlib", the compression library. Git won't build without it.

	- "ssh" is used to push and pull over the net.

	- A POSIX-compliant shell is required to run some scripts needed
	  for everyday use (e.g. "bisect", "request-pull").

	- "Perl" version 5.26.0 or later is needed to use some of the
	  features (e.g. sending patches using "git send-email",
	  interacting with svn repositories with "git svn").  If you can
	  live without these, use NO_PERL.  Note that recent releases of
	  Redhat/Fedora are reported to ship Perl binary package with some
	  core modules stripped away (see https://lwn.net/Articles/477234/),
	  so you might need to install additional packages other than Perl
	  itself, e.g. Digest::MD5, File::Spec, File::Temp, Net::Domain,
	  Net::SMTP, and Time::HiRes.

	- "libcurl" library is used for fetching and pushing
	  repositories over http:// or https://, as well as by
	  git-imap-send. If you do not need that functionality,
	  use NO_CURL to build without it.

	  Git requires version "7.61.0" or later of "libcurl" to build
	  without NO_CURL. This version requirement may be bumped in
	  the future.

	- "expat" library; git-http-push uses it for remote lock
	  management over DAV.  Similar to "curl" above, this is optional
	  (with NO_EXPAT).

	- "wish", the Tcl/Tk windowing shell is used in gitk to show the
	  history graphically, and in git-gui.  If you don't want gitk or
	  git-gui, you can use NO_TCLTK.

	- A gettext library is used by default for localizing Git. The
	  primary target is GNU libintl, but the Solaris gettext
	  implementation also works.

	  We need a gettext.h on the system for C code, gettext.sh (or
	  Solaris gettext(1)) for shell scripts, and libintl-perl for Perl
	  programs.

	  Set NO_GETTEXT to disable localization support and make Git only
	  use English. Under autoconf the configure script will do this
	  automatically if it can't find libintl on the system.

	- Python version 2.7 or later is needed to use the git-p4 interface
	  to Perforce.

 - Some platform specific issues are dealt with Makefile rules,
   but depending on your specific installation, you may not
   have all the libraries/tools needed, or you may have
   necessary libraries at unusual locations.  Please look at the
   top of the Makefile to see what can be adjusted for your needs.
   You can place local settings in config.mak and the Makefile
   will include them.  Note that config.mak is not distributed;
   the name is reserved for local settings.

 - To build and install documentation suite, you need to have
   the asciidoc/xmlto toolchain.  Because not many people are
   inclined to install the tools, the default build target
   ("make all") does _not_ build them.

   "make doc" builds documentation in man and html formats; there are
   also "make man", "make html" and "make info". Note that "make html"
   requires asciidoc, but not xmlto. "make man" (and thus make doc)
   requires both.

   "make install-doc" installs documentation in man format only; there
   are also "make install-man", "make install-html" and "make
   install-info".

   Building and installing the info file additionally requires
   makeinfo and docbook2X.  Version 0.8.3 is known to work.

   Building and installing the pdf file additionally requires
   dblatex.  Version >= 0.2.7 is known to work.

   All formats require at least asciidoc 8.4.1. Alternatively, you can
   use Asciidoctor (requires Ruby) by passing USE_ASCIIDOCTOR=YesPlease
   to make. You need at least Asciidoctor version 1.5.

   There are also "make quick-install-doc", "make quick-install-man"
   and "make quick-install-html" which install preformatted man pages
   and html documentation. To use these build targets, you need to
   clone two separate git-htmldocs and git-manpages repositories next
   to the clone of git itself.

   The minimum supported version of docbook-xsl is 1.74.

   Users attempting to build the documentation on Cygwin may need to ensure
   that the /etc/xml/catalog file looks something like this:

   <?xml version="1.0"?>
   <!DOCTYPE catalog PUBLIC
      "-//OASIS//DTD Entity Resolution XML Catalog V1.0//EN"
      "http://www.oasis-open.org/committees/entity/release/1.0/catalog.dtd"
   >
   <catalog xmlns="urn:oasis:names:tc:entity:xmlns:xml:catalog">
     <rewriteURI
       uriStartString = "http://docbook.sourceforge.net/release/xsl/current"
       rewritePrefix = "/usr/share/sgml/docbook/xsl-stylesheets"
     />
     <rewriteURI
       uriStartString="http://www.oasis-open.org/docbook/xml/4.5"
       rewritePrefix="/usr/share/sgml/docbook/xml-dtd-4.5"
     />
  </catalog>

  This can be achieved with the following two xmlcatalog commands:

  xmlcatalog --noout \
     --add rewriteURI \
        http://docbook.sourceforge.net/release/xsl/current \
        /usr/share/sgml/docbook/xsl-stylesheets \
     /etc/xml/catalog

  xmlcatalog --noout \
     --add rewriteURI \
         http://www.oasis-open.org/docbook/xml/4.5/xsl/current \
         /usr/share/sgml/docbook/xml-dtd-4.5 \
     /etc/xml/catalog