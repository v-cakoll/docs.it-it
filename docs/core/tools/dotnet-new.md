---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442241"
---
# <a name="dotnet-new"></a>dotnet new

**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a>Description

Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.

Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Arguments

- **`TEMPLATE`**

  Modello di cui creare un'istanza quando viene richiamato il comando. Ogni modello può avere opzioni specifiche che è possibile passare. Per altre informazioni, vedere [Opzioni del modello](#template-options).

  È possibile eseguire `dotnet new --list` o `dotnet new -l` per visualizzare un elenco di tutti i modelli installati. Se il `TEMPLATE` valore non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza della sottostringa su queste due colonne.

  A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in NuGet.org quando si richiama il `dotnet new` comando nelle condizioni seguenti:

  - Se l'interfaccia della riga di comando non riesce a trovare una corrispondenza del modello durante la chiamata `dotnet new` , non anche parziale.
  - Se è disponibile una versione più recente del modello. In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.

  Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK. Il linguaggio predefinito per il modello è indicato tra parentesi quadre. Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.

| Modelli                                    | Nome breve                      | Linguaggio     | Tag                                  | Introdotte |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| Applicazione console                          | [Console](#console)             | [C#], F#, VB | Comune/Console                        | 1.0        |
| Libreria di classi                                | [classlib](#classlib)           | [C#], F#, VB | Comune/Library                        | 1.0        |
| Applicazione WPF                              | [WPF](#wpf)                     | [C#]         | Common/WPF                            | 3.0        |
| Libreria di classi WPF                            | [wpflib](#wpf)                  | [C#]         | Common/WPF                            | 3.0        |
| Libreria di controlli personalizzati WPF                   | [wpfcustomcontrollib](#wpf)     | [C#]         | Common/WPF                            | 3.0        |
| Libreria di controlli utente WPF                     | [wpfusercontrollib](#wpf)       | [C#]         | Common/WPF                            | 3.0        |
| Applicazione Windows Forms (WinForms)         | [WinForms](#winforms)           | [C#]         | Comune/Windows Form                       | 3.0        |
| Libreria di classi Windows Forms (WinForms)       | [winformslib](#winforms)        | [C#]         | Comune/Windows Form                       | 3.0        |
| Servizio ruolo di lavoro                               | [lavoro](#web-others)           | [C#]         | Comune/di lavoro/Web                     | 3.0        |
| Progetto unit test                            | [MSTest](#test)                 | [C#], F#, VB | Test/MSTest                           | 1.0        |
| Progetto di test NUnit 3                         | [NUnit](#nunit)                  | [C#], F#, VB | Test/NUnit                            | 2.1.400    |
| Elemento di test NUnit 3                            | `nunit-test`                    | [C#], F#, VB | Test/NUnit                            | 2.2        |
| Progetto di test xUnit                           | [xUnit](#test)                  | [C#], F#, VB | Test/xUnit                            | 1.0        |
| Componente Razor                              | `razorcomponent`                | [C#]         | Web/ASP.NET                           | 3.0        |
| Pagina Razor                                   | [pagina](#page)                   | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewImports                              | [viewimports](#namespace)       | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewStart                                | `viewstart`                     | [C#]         | Web/ASP.NET                           | 2.0        |
| App Server Blazer                            | [blazorserver](#blazorserver)   | [C#]         | Web/Blazer                            | 3.0        |
| Progetto ASP.NET Core vuoto                           | [Web](#web)                     | [C#], F#     | Web/Vuoto                             | 1.0        |
| App Web ASP.NET Core (Model-View-Controller) | [MVC](#web-options)             | [C#], F#     | Web/MVC                               | 1.0        |
| App Web ASP.NET Core                         | [WebApp, Razor](#web-options)   | [C#]         | Web/MVC/Razor Pages                   | 2,2, 2,0   |
| ASP.NET Core con Angular                    | [angolare](#spa)                 | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js                   | [React](#spa)                   | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js e Redux         | [reactredux](#reactredux)       | [C#]         | Web/MVC/SPA                           | 2.0        |
| Libreria di classi Razor                          | [razorclasslib](#razorclasslib) | [C#]         | Web/Razor/Libreria/Libreria di classi Razor | 2.1        |
| API Web ASP.NET Core                         | [WebAPI](#webapi)               | [C#], F#     | Web/WebAPI                            | 1.0        |
| Servizio ASP.NET Core gRPC                    | [grpc](#web-others)             | [C#]         | Web/gRPC                              | 3.0        |
| file gitignore DotNet                        | `gitignore`                     |              | File di configurazione                                | 3.0        |
| File global.json                             | [globaljson](#globaljson)       |              | File di configurazione                                | 2.0        |
| Configurazione NuGet                                 | `nugetconfig`                   |              | File di configurazione                                | 1.0        |
| File manifesto dello strumento locale DotNet              | `tool-manifest`                 |              | File di configurazione                                | 3.0        |
| Configurazione Web                                   | `webconfig`                     |              | File di configurazione                                | 1.0        |
| File di soluzione                                | `sln`                           |              | Soluzione                              | 1.0        |
| File buffer del protocollo                         | [proto](#namespace)             |              | Web/gRPC                              | 3.0        |

## <a name="options"></a>Opzioni

- **`--dry-run`**

  Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello. Disponibile a partire da .NET Core 2,2 SDK.

- **`--force`**

  Forza la generazione del contenuto anche se ciò modifica i file esistenti. Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.

- **`-h|--help`**

  Stampa la Guida per il comando. Può essere richiamato per il `dotnet new` comando stesso o per qualsiasi modello. Ad esempio: `dotnet new mvc --help`.

- **`-i|--install <PATH|NUGET_ID>`**

  Installa un pacchetto di modelli dall'oggetto `PATH` o `NUGET_ID` fornito. Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`. Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione stabile più recente del pacchetto. Vedere un esempio nella sezione degli [esempi](#examples) .
  
  Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.

  Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).

- **`-l|--list`**

  Elenca i modelli contenenti il nome specificato. Se non viene specificato alcun nome, elenca tutti i modelli.

- **`-lang|--language {C#|F#|VB}`**

  Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

  > [!NOTE]
  > Alcune shell interpretano `#` come un carattere speciale. In questi casi, racchiudere il valore del parametro Language tra virgolette. Ad esempio: `dotnet new console -lang "F#"`.

- **`-n|--name <OUTPUT_NAME>`**

  Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

- **`--nuget-source <SOURCE>`**

  Specifica un'origine NuGet da usare durante l'installazione. Disponibile a partire da .NET Core 2,1 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

- **`--type <TYPE>`**

  Filtra i modelli in base ai tipi disponibili. I valori predefiniti sono `project` , `item` e `other` .

- **`-u|--uninstall [PATH|NUGET_ID]`**

  Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito. Quando il `<PATH|NUGET_ID>` valore non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati. Quando si specifica `NUGET_ID` , non includere il numero di versione.

  Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.

  > [!NOTE]
  > Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo. Ad esempio, *C:/Users/ \< User>/Documents/templates/garciasoftware.consoletemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che lo contiene.
  > Non includere una barra di directory finale terminata nel percorso del modello.

- **`--update-apply`**

  Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa. Disponibile a partire da .NET Core 3.0 SDK.

- **`--update-check`**

  Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati. Disponibile a partire da .NET Core 3.0 SDK.

## <a name="template-options"></a>Opzioni del modello

Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive. I modelli principali includono le opzioni aggiuntive seguenti:

### <a name="console"></a>console

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Disponibile a partire da .NET Core 3.0 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  Imposta la `LangVersion` proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#. Disponibile a partire da .NET Core 2,2 SDK.

  Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Se specificato, non esegue un ripristino implicito durante la creazione del progetto. Disponibile a partire da .NET Core 2,2 SDK.

***

### <a name="classlib"></a>classlib

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard. Il valore predefinito è `netstandard2.0`.

- **`--langVersion <VERSION_NUMBER>`**

  Imposta la `LangVersion` proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#. Disponibile a partire da .NET Core 2,2 SDK.

  Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a>WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Il valore predefinito è `netcoreapp3.1`. Disponibile a partire da .NET Core 3,1 SDK.

- **`--langVersion <VERSION_NUMBER>`**

  Imposta la `LangVersion` proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.

  Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="winforms-winformslib"></a><a name="winforms"></a>WinForms, winformslib

- **`--langVersion <VERSION_NUMBER>`**

  Imposta la `LangVersion` proprietà nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.

  Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="worker-grpc"></a><a name="web-others"></a>Worker, grpc

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Il valore predefinito è `netcoreapp3.1`. Disponibile a partire da .NET Core 3,1 SDK.

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="mstest-xunit"></a><a name="test"></a>MSTest, xUnit

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione disponibile a partire da .NET Core 3,0 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="nunit"></a>NUnit

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.2         | `netcoreapp2.2` |
  | 2.1         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="page"></a>pagina

- **`-na|--namespace <NAMESPACE_NAME>`**

  Spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

- **`-np|--no-pagemodel`**

  Crea la pagina senza PageModel.

***

### <a name="viewimports-proto"></a><a name="namespace"></a>viewimports, proto

- **`-na|--namespace <NAMESPACE_NAME>`**

  Spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

***

### <a name="blazorserver"></a>blazorserver

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `MultiOrg`: autenticazione aziendale per più tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID dei criteri di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  ID dei criteri di reimpostazione della password per il progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  ID dei criteri di modifica del profilo per il progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per il progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del tenant di directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

- **`-r|--org-read-access`**

  Consente all'applicazione di accedere in lettura alla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si applica solo se `Individual` ,, `IndividualB2C` `SingleOrg` o `MultiOrg` non vengono utilizzati per `--auth` .

- **`-uld|--use-local-db`**

  Specifica il database locale da usare anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

***

### <a name="web"></a>Web

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2,2 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

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

### <a name="mvc-webapp"></a><a name="web-options"></a>MVC, webapp

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `MultiOrg`: autenticazione aziendale per più tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID dei criteri di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  ID dei criteri di reimpostazione della password per il progetto. Usare con l'autenticazione `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  ID dei criteri di modifica del profilo per il progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per il progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del tenant di directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

- **`-r|--org-read-access`**

  Consente all'applicazione di accedere in lettura alla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

- **`-uld|--use-local-db`**

  Specifica il database locale da usare anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione disponibile a partire da .NET Core 3,0 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--use-browserlink`**

  Include BrowserLink nel progetto. Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.

- **`-rrc|--razor-runtime-compilation`**

  Determina se il progetto è configurato per usare la [compilazione del runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle build di debug. Opzione disponibile a partire da .NET Core 3.1.201 SDK.

***

### <a name="angular-react"></a><a name="spa"></a>angolare, React

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. Disponibile a partire da .NET Core 3.0 SDK.
  
  I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `Individual`: autenticazione singola.

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la creazione del progetto.

- **`--no-https`**

  Disattiva HTTPS. Questa opzione si applica solo se l'autenticazione è `None` .

- **`-uld|--use-local-db`**

  Specifica il database locale da usare anziché SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`. Disponibile a partire da .NET Core 3.0 SDK.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2,2 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

  | Versione dell'SDK | Valore predefinito   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

***

### <a name="reactredux"></a>reactredux

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2,2 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

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

  Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria. Disponibile a partire da .NET Core 3.0 SDK.

***
  
### <a name="webapi"></a>webapi

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo di autenticazione da usare. I valori possibili sono:

  - `None`: nessuna autenticazione (valore predefinito).
  - `IndividualB2C`: singola autenticazione con Azure AD B2C.
  - `SingleOrg`: autenticazione aziendale per un singolo tenant.
  - `Windows`: autenticazione di Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  ID dei criteri di accesso e di iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  ID client per il progetto. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del tenant di directory. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `qualified.domain.name`.

- **`--tenant-id <ID>`**

  ID TenantId della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

- **`-r|--org-read-access`**

  Consente all'applicazione di accedere in lettura alla directory. Si applica solo all' `SingleOrg` autenticazione di.

- **`--exclude-launch-settings`**

  Esclude *launchSettings. JSON* dal modello generato.

- **`--no-https`**

  Disattiva HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si applica solo se `IndividualB2C` o `SingleOrg` non vengono usati per l'autenticazione.

- **`-uld|--use-local-db`**

  Specifica il database locale da usare anziché SQLite. Si applica solo all' `IndividualB2C` autenticazione di.

- **`-f|--framework <FRAMEWORK>`**

  Specifica il [Framework](../../standard/frameworks.md) di destinazione. Opzione non disponibile in .NET Core 2,2 SDK.

  La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:

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

  Specifica la versione del .NET Core SDK da usare nel file *Global. JSON* .

***

## <a name="examples"></a>Esempi

- Creare un progetto di applicazione console C# specificando il nome del modello:

  ```dotnetcli
  dotnet new "Console Application"
  ```

- Creare un progetto di applicazione console F# nella directory corrente:

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- Creare un progetto libreria di classi .NET Standard nella directory specificata:

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

- Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:

  ```dotnetcli
  dotnet new -u
  ```

- Creare un file *Global. JSON* nella directory corrente impostando la versione dell'SDK su 3.1.101:

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a>Vedere anche

- [Modelli personalizzati per dotnet new](custom-templates.md)
- [Creare un modello personalizzato per dotnet new](../tutorials/cli-templates-create-item-template.md)
- [Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Modelli disponibili per dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
