---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399126"
---
# <a name="dotnet-new"></a>dotnet new

**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a>Descrizione

Il `dotnet new` comando crea un progetto .NET Core o altri elementi basati su un modello.

Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.

## <a name="arguments"></a>Argomenti

- **`TEMPLATE`**

  Modello di cui creare un'istanza quando viene richiamato il comando. Ogni modello può avere opzioni specifiche che è possibile passare. Per altre informazioni, vedere [Opzioni del modello](#template-options).

  È possibile `dotnet new --list` eseguire per visualizzare un elenco di tutti i modelli installati. Se `TEMPLATE` il valore non corrisponde esattamente al testo nella colonna **Templates** o **Short Name** della tabella restituita, viene eseguita una corrispondenza di sottostringhe su queste due colonne.

  A partire da .NET Core 3.0 SDK, l'interfaccia `dotnet new` della riga di comando cerca i modelli in NuGet.org quando si richiama il comando nelle condizioni seguenti:

  - Se l'interfaccia della riga di comando `dotnet new`non riesce a trovare una corrispondenza del modello quando si richiama , nemmeno parziale.
  - Se è disponibile una versione più recente del modello. In questo caso, il progetto o l'elemento viene creato, ma l'interfaccia della riga di comando avvisa l'utente di una versione aggiornata del modello.

  Il comando contiene un elenco predefinito di modelli. Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili. Nella tabella seguente vengono illustrati i modelli preinstallati con .NET Core SDK. Il linguaggio predefinito per il modello è indicato tra parentesi quadre. Fare clic sul collegamento del nome breve per visualizzare le opzioni del modello specifico.

| Modelli                                    | Nome breve                      | Linguaggio     | Tag                                  | Presentare |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| Applicazione console                          | [console](#console)             | [C#], F#, VB | Comune/Console                        | 1.0        |
| Libreria di classi                                | [classlib](#classlib)           | [C#], F#, VB | Comune/Library                        | 1.0        |
| Applicazione WPF                              | [Wpf](#wpf)                     | [C#]         | Comune/WPF                            | 3.0        |
| Libreria di classi WPFWPF Class library                            | [wpflib (libreria)](#wpf)                  | [C#]         | Comune/WPF                            | 3.0        |
| Libreria di controlli personalizzati WPF                   | [wpfcustomcontrollib](#wpf)     | [C#]         | Comune/WPF                            | 3.0        |
| Libreria di controlli utente WPF                     | [wpfusercontrollib](#wpf)       | [C#]         | Comune/WPF                            | 3.0        |
| Applicazione Windows Form (WinForms)         | [Winforms](#winforms)           | [C#]         | Comune/WinForms                       | 3.0        |
| Libreria di classi Windows Form (WindowsForms)       | [winformslib](#winforms)        | [C#]         | Comune/WinForms                       | 3.0        |
| Servizio di lavoro                               | [Lavoratore](#web-others)           | [C#]         | Comune/Lavoratore/Web                     | 3.0        |
| Progetto unit test                            | [Mstest](#test)                 | [C#], F#, VB | Test/MSTest                           | 1.0        |
| Progetto di test NUnit 3                         | [Nunit](#nunit)                  | [C#], F#, VB | Test/NUnit                            | 2.1.400    |
| Elemento di test NUnit 3                            | `nunit-test`                    | [C#], F#, VB | Test/NUnit                            | 2.2        |
| Progetto di test xUnit                           | [xunit](#test)                  | [C#], F#, VB | Test/xUnit                            | 1.0        |
| Componente Razor                              | `razorcomponent`                | [C#]         | Web/ASP.NET                           | 3.0        |
| Pagina Razor                                   | [Pagina](#page)                   | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewImports                              | [viewimports](#namespace)       | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewStart                                | `viewstart`                     | [C#]         | Web/ASP.NET                           | 2.0        |
| Blazor Server App                            | [blazorservere](#blazorserver)   | [C#]         | Web/Blazor                            | 3.0        |
| Progetto ASP.NET Core vuoto                           | [Web](#web)                     | [C#], F#     | Web/Vuoto                             | 1.0        |
| App Web ASP.NET Core (Model-View-Controller) | [Mvc](#web-options)             | [C#], F#     | Web/MVC                               | 1.0        |
| App Web ASP.NET Core                         | [webapp, rasoio](#web-options)   | [C#]         | Web/MVC/Razor Pages                   | 2.2, 2.0   |
| ASP.NET Core con Angular                    | [Angolare](#spa)                 | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js                   | [Reagire](#spa)                   | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js e Redux         | [reactredux](#reactredux)       | [C#]         | Web/MVC/SPA                           | 2.0        |
| Libreria di classi Razor                          | [razorclasslib](#razorclasslib) | [C#]         | Web/Razor/Libreria/Libreria di classi Razor | 2.1        |
| API Web ASP.NET Core                         | [webapi](#webapi)               | [C#], F#     | Web/WebAPI                            | 1.0        |
| ASP.NET core del servizio gRPC                    | [grpc](#web-others)             | [C#]         | Web/gRPC                              | 3.0        |
| File buffer protocollo                         | [Proto](#namespace)             |              | Web/gRPC                              | 3.0        |
| file gitignore dotnet                        | `gitignore`                     |              | File di configurazione                                | 3.0        |
| File global.json                             | [globaljson](#globaljson)       |              | File di configurazione                                | 2.0        |
| Configurazione NuGet                                 | `nugetconfig`                   |              | File di configurazione                                | 1.0        |
| dotnet file manifesto dello strumento locale              | `tool-manifest`                 |              | File di configurazione                                | 3.0        |
| Configurazione Web                                   | `webconfig`                     |              | File di configurazione                                | 1.0        |
| File di soluzione                                | `sln`                           |              | Soluzione                              | 1.0        |

## <a name="options"></a>Opzioni

- **`--dry-run`**

  Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito. Disponibile da .NET Core 2.2 SDK.

- **`--force`**

  Forza la generazione del contenuto anche se ciò modifica i file esistenti. Questa operazione è necessaria quando il modello scelto sovrascriverà i file esistenti nella directory di output.

- **`-h|--help`**

  Stampa la Guida per il comando. Può essere richiamato `dotnet new` per il comando stesso o per qualsiasi modello. Ad esempio: `dotnet new mvc --help`.

- **`-i|--install <PATH|NUGET_ID>`**

  Installa un pacchetto di `PATH` `NUGET_ID` modelli da o fornito. Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`. Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione del pacchetto stabile più recente. Vedere un esempio nella sezione [Esempi.See](#examples) an example in the Examples section.
  
  Se una versione del modello è già stata installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente se non è stata specificata alcuna versione.

  Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).

- **`-l|--list`**

  Elenca i modelli contenenti il nome specificato. Se non viene specificato alcun nome, vengono elencati tutti i modelli.

- **`-lang|--language {C#|F#|VB}`**

  Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

  > [!NOTE]
  > Alcune shell interpretano `#` come un carattere speciale. In questi casi, racchiudere il valore del parametro del linguaggio tra virgolette. Ad esempio: `dotnet new console -lang "F#"`.

- **`-n|--name <OUTPUT_NAME>`**

  Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

- **`--nuget-source`**

  Specifica un'origine NuGet da usare durante l'installazione. Disponibile da .NET Core 2.1 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

- **`--type`**

  Filtra i modelli in base ai tipi disponibili. I valori predefiniti sono "project", "item" o "other".

- **`-u|--uninstall [PATH|NUGET_ID]`**

  Disinstalla un pacchetto di `PATH` `NUGET_ID` modelli nel file o fornito. Quando `<PATH|NUGET_ID>` il valore non è specificato, vengono visualizzati tutti i modelli di modello attualmente installati e i modelli associati. Quando si `NUGET_ID`specifica , non includere il numero di versione.

  Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.

  > [!NOTE]
  > Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo. Ad esempio, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che la contiene non funzionerà.
  > Non includere una barra di terminazione finale nel percorso del modello.

- **`--update-apply`**

  Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati e li installa. Disponibile a partire da .NET Core 3.0 SDK.

- **`--update-check`**

  Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati. Disponibile a partire da .NET Core 3.0 SDK.

## <a name="template-options"></a>Opzioni del modello

Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive. I modelli principali includono le opzioni aggiuntive seguenti:

### <a name="console"></a>console

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Disponibile a partire da .NET Core 3.0 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  Imposta `LangVersion` la proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#. Disponibile da .NET Core 2.2 SDK.

  Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Se specificato, non esegue un ripristino implicito durante la creazione del progetto. Disponibile da .NET Core 2.2 SDK.

***

### <a name="classlib"></a>classlib

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard. Il valore predefinito è `netstandard2.0`.

- **`--langVersion <VERSION_NUMBER>`**

  Imposta `LangVersion` la proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#. Disponibile da .NET Core 2.2 SDK.

  Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="wpf"></a>wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Il valore predefinito è `netcoreapp3.1`. Disponibile da .NET Core 3.1 SDK.

- **`--langVersion <VERSION_NUMBER>`**

  Imposta `LangVersion` la proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.

  Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="winforms"></a>winforms, winformslib

- **`--langVersion <VERSION_NUMBER>`**

  Imposta `LangVersion` la proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.

  Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="web-others"></a>lavoratore, grpc

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Il valore predefinito è `netcoreapp3.1`. Disponibile da .NET Core 3.1 SDK.

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="test"></a>mstest, xunit

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione disponibile da .NET Core 3.0 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="nunit"></a>Nunit

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.2         | `netcoreapp2.2` |
  | 2.1         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="page"></a>pagina

- **`-na|--namespace <NAMESPACE_NAME>`**

  Spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

- **`-np|--no-pagemodel`**

  Crea la pagina senza un PageModel.

***

### <a name="namespace"></a>viewimports, proto

- **`-na|--namespace <NAMESPACE_NAME>`**

  Spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

***

### <a name="blazorserver"></a>blazorservere

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `MultiOrg`: autenticazione aziendale per più tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza B2C di Azure Active Directory a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID del criterio di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  ID criterio password di reimpostazione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  ID dei criteri del profilo di modifica per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per questo progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

- **`-r|--org-read-access`**

  Consente all'applicazione l'accesso in lettura alla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si `Individual` `IndividualB2C`applica `SingleOrg`solo `MultiOrg` se , , `--auth`o non vengono utilizzati per .

- **`-uld|--use-local-db`**

  Specifica che deve essere utilizzato LocalDB anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="web"></a>Web

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2.2 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--no-https`**

  Disattiva HTTPS.

***

### <a name="web-options"></a>mvc, webapp

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `MultiOrg`: autenticazione aziendale per più tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza B2C di Azure Active Directory a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID del criterio di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  ID criterio password di reimpostazione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  ID dei criteri del profilo di modifica per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per questo progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

- **`-r|--org-read-access`**

  Consente all'applicazione l'accesso in lettura alla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

- **`-uld|--use-local-db`**

  Specifica che deve essere utilizzato LocalDB anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione disponibile da .NET Core 3.0 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--use-browserlink`**

  Include BrowserLink nel progetto. Opzione non disponibile in .NET Core 2.2 e 3.1 SDK.

***

### <a name="spa"></a>angolare, reagire

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. Disponibile a partire da .NET Core 3.0 SDK.
  
  I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si applica `None`solo se l'autenticazione è .

- **`-uld|--use-local-db`**

  Specifica che deve essere utilizzato LocalDB anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`. Disponibile a partire da .NET Core 3.0 SDK.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2.2 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

***

### <a name="reactredux"></a>reactredux

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2.2 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--no-https`**

  Disattiva HTTPS.

***

### <a name="razorclasslib"></a>razorclasslib

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`-s|--support-pages-and-views`**

  Supporta l'aggiunta di pagine e viste Razor tradizionali oltre ai componenti di questa libreria. Disponibile a partire da .NET Core 3.0 SDK.

***
  
### <a name="webapi"></a>webapi

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza B2C di Azure Active Directory a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID del criterio di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per questo progetto. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio per il tenant della directory. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`-r|--org-read-access`**

  Consente all'applicazione l'accesso in lettura alla directory. Si applica `SingleOrg` solo all'autenticazione.

- **`--exclude-launch-settings`**

  Esclude *launchSettings.json* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si `IndividualB2C` `SingleOrg` applica solo se o non vengono utilizzati per l'autenticazione.

- **`-uld|--use-local-db`**

  Specifica che deve essere utilizzato LocalDB anziché SQLite. Si applica `IndividualB2C` solo all'autenticazione.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2.2 SDK.

  Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="globaljson"></a>globaljson

- **`--sdk-version <VERSION_NUMBER>`**

  Specifica la versione di .NET Core SDK da utilizzare nel file *global.json.*

***

## <a name="examples"></a>Esempi

- Creare un progetto di applicazione console C# specificando il nome del modello:

  ```dotnetcli
  dotnet new "Console Application"
  ```

- Creare un progetto di applicazione console F# nella directory corrente:

  ```dotnetcli
  dotnet new console -lang F#
  ```

- Creare un progetto di libreria di classi .NET Standard nella directory specificata:Create a .NET Standard class library project in the specified directory:

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:

  ```dotnetcli
  dotnet new mvc -au None
  ```

- Creare un nuovo progetto xUnit:

  ```dotnetcli
  dotnet new xunit
  ```

- Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):

  ```dotnetcli
  dotnet new spa -l
  ```

- Elencare tutti i modelli corrispondenti alla sottostringa *we*. La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.

  ```dotnetcli
  dotnet new we -l
  ```

- Provare a richiamare il modello corrispondente a *ng*. Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.

  ```dotnetcli
  dotnet new ng
  ```

- Installare la versione 2.0 dei modelli SPA per ASP.NET Core:

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- Elencare i modelli installati e i dettagli su di essi, tra cui come disinstallarli:

  ```dotnetcli
  dotnet new -u
  ```

- Creare un *file global.json* nella directory corrente impostando la versione SDK su 3.1.101:

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a>Vedere anche

- [Modelli personalizzati per dotnet new](custom-templates.md)
- [Creare un modello personalizzato per dotnet new](../tutorials/cli-templates-create-item-template.md)
- [Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Modelli disponibili per dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
