---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 05/06/2019
ms.openlocfilehash: b61b5fd53f470c30b636026fa19ebfad834d6354
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117677"
---
# <a name="dotnet-new"></a>dotnet new

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.

## <a name="synopsis"></a>Riepilogo

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a>Descrizione

Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.

Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.

## <a name="arguments"></a>Argomenti

`TEMPLATE`

Modello di cui creare un'istanza quando viene richiamato il comando. Ogni modello può avere opzioni specifiche che è possibile passare. Per altre informazioni, vedere [Opzioni del modello](#template-options).

Se il valore di `TEMPLATE` non è una corrispondenza esatta del testo nella colonna **Modelli** o **Nome breve** viene eseguita una corrispondenza sottostringa in queste due colonne.

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

Il comando contiene un elenco predefinito di modelli. Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili. La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.2.100. Il linguaggio predefinito per il modello è indicato tra parentesi quadre.

| Modelli                                    | Nome breve        | Linguaggio     | Tag                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| Applicazione console                          | `console`         | [C#], F#, VB | Comune/Console                        |
| Libreria di classi                                | `classlib`        | [C#], F#, VB | Comune/Library                        |
| Progetto unit test                            | `mstest`          | [C#], F#, VB | Test/MSTest                           |
| Progetto di test NUnit 3                         | `nunit`           | [C#], F#, VB | Test/NUnit                            |
| Elemento di test NUnit 3                            | `nunit-test`      | [C#], F#, VB | Test/NUnit                            |
| Progetto di test xUnit                           | `xunit`           | [C#], F#, VB | Test/xUnit                            |
| Pagina Razor                                   | `page`            | [C#]         | Web/ASP.NET                           |
| MVC ViewImports                              | `viewimports`     | [C#]         | Web/ASP.NET                           |
| MVC ViewStart                                | `viewstart`       | [C#]         | Web/ASP.NET                           |
| Progetto ASP.NET Core vuoto                           | `web`             | [C#], F#     | Web/Vuoto                             |
| App Web ASP.NET Core (Model-View-Controller) | `mvc`             | [C#], F#     | Web/MVC                               |
| App Web ASP.NET Core                         | `webapp`, `razor` | [C#]         | Web/MVC/Razor Pages                   |
| ASP.NET Core con Angular                    | `angular`         | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js                   | `react`           | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js e Redux         | `reactredux`      | [C#]         | Web/MVC/SPA                           |
| Libreria di classi Razor                          | `razorclasslib`   | [C#]         | Web/Razor/Libreria/Libreria di classi Razor |
| API Web ASP.NET Core                         | `webapi`          | [C#], F#     | Web/WebAPI                            |
| File global.json                             | `globaljson`      |              | Config                                |
| Configurazione NuGet                                 | `nugetconfig`     |              | Config                                |
| Configurazione Web                                   | `webconfig`       |              | Config                                |
| File di soluzione                                | `sln`             |              | Soluzione                              |

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

Il comando contiene un elenco predefinito di modelli. Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili. La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300. Il linguaggio predefinito per il modello è indicato tra parentesi quadre.

| Modelli                                    | Nome breve      | Linguaggio     | Tag                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| Applicazione console                          | `console`       | [C#], F#, VB | Comune/Console                        |
| Libreria di classi                                | `classlib`      | [C#], F#, VB | Comune/Library                        |
| Progetto unit test                            | `mstest`        | [C#], F#, VB | Test/MSTest                           |
| Progetto di test xUnit                           | `xunit`         | [C#], F#, VB | Test/xUnit                            |
| Pagina Razor                                   | `page`          | [C#]         | Web/ASP.NET                           |
| MVC ViewImports                              | `viewimports`   | [C#]         | Web/ASP.NET                           |
| MVC ViewStart                                | `viewstart`     | [C#]         | Web/ASP.NET                           |
| Progetto ASP.NET Core vuoto                           | `web`           | [C#], F#     | Web/Vuoto                             |
| App Web ASP.NET Core (Model-View-Controller) | `mvc`           | [C#], F#     | Web/MVC                               |
| App Web ASP.NET Core                         | `razor`         | [C#]         | Web/MVC/Razor Pages                   |
| ASP.NET Core con Angular                    | `angular`       | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js                   | `react`         | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js e Redux         | `reactredux`    | [C#]         | Web/MVC/SPA                           | 
| Libreria di classi Razor                          | `razorclasslib` | [C#]         | Web/Razor/Libreria/Libreria di classi Razor |
| API Web ASP.NET Core                         | `webapi`        | [C#], F#     | Web/WebAPI                            |
| File global.json                             | `globaljson`    |              | Config                                |
| Configurazione NuGet                                 | `nugetconfig`   |              | Config                                |
| Configurazione Web                                   | `webconfig`     |              | Config                                |
| File di soluzione                                | `sln`           |              | Soluzione                              |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

Il comando contiene un elenco predefinito di modelli. Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili. La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.0. Il linguaggio predefinito per il modello è indicato tra parentesi quadre.

| Modelli                                    | Nome breve    | Linguaggio     | Tag                |
|----------------------------------------------|---------------|--------------|---------------------|
| Applicazione console                          | `console`     | [C#], F#, VB | Comune/Console      |
| Libreria di classi                                | `classlib`    | [C#], F#, VB | Comune/Library      |
| Progetto unit test                            | `mstest`      | [C#], F#, VB | Test/MSTest         |
| Progetto di test xUnit                           | `xunit`       | [C#], F#, VB | Test/xUnit          |
| Progetto ASP.NET Core vuoto                           | `web`         | [C#], F#     | Web/Vuoto           |
| App Web ASP.NET Core (Model-View-Controller) | `mvc`         | [C#], F#     | Web/MVC             |
| App Web ASP.NET Core                         | `razor`       | [C#]         | Web/MVC/Razor Pages |
| ASP.NET Core con Angular                    | `angular`     | [C#]         | Web/MVC/SPA         |
| ASP.NET Core con React.js                   | `react`       | [C#]         | Web/MVC/SPA         |
| ASP.NET Core con React.js e Redux         | `reactredux`  | [C#]         | Web/MVC/SPA         |
| API Web ASP.NET Core                         | `webapi`      | [C#], F#     | Web/WebAPI          |
| File global.json                             | `globaljson`  |              | Config              |
| Configurazione Nuget                                 | `nugetconfig` |              | Config              |
| Configurazione Web                                   | `webconfig`   |              | Config              |
| File di soluzione                                | `sln`         |              | Soluzione            |
| Pagina Razor                                   | `page`        |              | Web/ASP.NET         |
| MVC ViewImports                              | `viewimports` |              | Web/ASP.NET         |
| MVC ViewStart                                | `viewstart`   |              | Web/ASP.NET         |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Il comando contiene un elenco predefinito di modelli. Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili. La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.0.1. Il linguaggio predefinito per il modello è indicato tra parentesi quadre.

| Modelli            | Nome breve    | Linguaggio | Tag           |
|----------------------|---------------|----------|----------------|
| Applicazione console  | `console`     | [C#], F# | Comune/Console |
| Libreria di classi        | `classlib`    | [C#], F# | Comune/Library |
| Progetto unit test    | `mstest`      | [C#], F# | Test/MSTest    |
| Progetto di test xUnit   | `xunit`       | [C#], F# | Test/xUnit     |
| Progetto ASP.NET Core vuoto   | `web`         | [C#]     | Web/Vuoto      |
| App Web ASP.NET Core | `mvc`         | [C#], F# | Web/MVC        |
| API Web ASP.NET Core | `webapi`      | [C#]     | Web/WebAPI     |
| Configurazione Nuget         | `nugetconfig` |          | Config         |
| Configurazione Web           | `webconfig`   |          | Config         |
| File di soluzione        | `sln`         |          | Soluzione       |

---

## <a name="options"></a>Opzioni

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

`--dry-run`

Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.

`--force`

Forza la generazione del contenuto anche se ciò modifica i file esistenti. Questo è necessario quando la directory di output contiene già un progetto.

`-h|--help`

Stampa la Guida per il comando. Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito. Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`. Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto. Per un esempio, vedere la sezione [Esempi](#examples).

Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).

`-l|--list`

Elenca i modelli contenenti il nome specificato. Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata. Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.

`-lang|--language {C#|F#|VB}`

Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

> [!NOTE]
> Alcune shell interpretano `#` come un carattere speciale. In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

`--nuget-source`

Specifica un'origine NuGet da usare durante l'installazione.

`-o|--output <OUTPUT_DIRECTORY>`

Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

`--type`

Filtra i modelli in base ai tipi disponibili. I valori predefiniti sono "project", "item" o "other".

`-u|--uninstall <PATH|NUGET_ID>`

Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito. Quando si esclude il valore di `<PATH|NUGET_ID>` vengono visualizzati tutti i pacchetti di modelli attualmente installati e i relativi modelli associati.

> [!NOTE]
> Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo. Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.
> Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force`

Forza la generazione del contenuto anche se ciò modifica i file esistenti. Questo è necessario quando la directory di output contiene già un progetto.

`-h|--help`

Stampa la Guida per il comando. Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito. Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`. Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto. Per un esempio, vedere la sezione [Esempi](#examples).

Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).

`-l|--list`

Elenca i modelli contenenti il nome specificato. Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata. Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.

`-lang|--language {C#|F#|VB}`

Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

> [!NOTE]
> Alcune shell interpretano `#` come un carattere speciale. In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

`--nuget-source`

Specifica un'origine NuGet da usare durante l'installazione.

`-o|--output <OUTPUT_DIRECTORY>`

Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

`--type`

Filtra i modelli in base ai tipi disponibili. I valori predefiniti sono "project", "item" o "other".

`-u|--uninstall <PATH|NUGET_ID>`

Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.

> [!NOTE]
> Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo. Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.
> Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force`

Forza la generazione del contenuto anche se ciò modifica i file esistenti. Questo è necessario quando la directory di output contiene già un progetto.

`-h|--help`

Stampa la Guida per il comando. Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito. Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`. Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto. Per un esempio, vedere la sezione [Esempi](#examples).

Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).

`-l|--list`

Elenca i modelli contenenti il nome specificato. Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata. Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.

`-lang|--language {C#|F#|VB}`

Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

> [!NOTE]
> Alcune shell interpretano `#` come un carattere speciale. In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

`-o|--output <OUTPUT_DIRECTORY>`

Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

`--type`

Filtra i modelli in base ai tipi disponibili. I valori predefiniti sono "project", "item" o "other".

`-u|--uninstall <PATH|NUGET_ID>`

Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.

> [!NOTE]
> Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo. Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà. Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.
> 
> Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-all|--show-all`

Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi. Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione. Questo è necessario quando la directory di output contiene già un progetto.

`-h|--help`

Stampa la Guida per il comando. Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.

`-l|--list`

Elenca i modelli contenenti il nome specificato. Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata. Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.

`-lang|--language {C#|F#}`

Linguaggio del modello da creare. Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments). Non è valido per alcuni modelli.

> [!NOTE]
> Alcune shell interpretano `#` come un carattere speciale. In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Nome dell'output creato. Se non viene specificato alcun nome, viene usato il nome della directory corrente.

`-o|--output <OUTPUT_DIRECTORY>`

Percorso in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

---

## <a name="template-options"></a>Opzioni del modello

Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive. I modelli principali includono le opzioni aggiuntive seguenti:

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

**console**

`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**angular, react, reactredux**

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

`--no-https`: il progetto non richiede HTTPS. Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.

**razorclasslib**

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**classlib**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp2.2` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard. Il valore predefinito è `netstandard2.0`.

`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato. Ad esempio, usare `--langVersion 7.3` per usare C# 7.3. Non supportata per F#.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**mstest, xunit**

`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**nunit**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Il valore predefinito è `netcoreapp2.1`.

`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**page**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la pagina senza un PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

**web**

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

`--no-https`: il progetto non richiede HTTPS. Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.

**mvc, webapp**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `Individual`: autenticazione singola.
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `MultiOrg`: autenticazione aziendale per più tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--no-https`: il progetto non richiede HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--no-https`: il progetto non richiede HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

**console, angular, react, reactredux, razorclasslib**

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**classlib**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp2.1` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard. Il valore predefinito è `netstandard2.0`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**mstest, xunit**

`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.

**web**

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

`--no-https`: il progetto non richiede HTTPS. Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

`--no-https`: il progetto non richiede HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `Individual`: autenticazione singola.
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `MultiOrg`: autenticazione aziendale per più tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.

`--use-browserlink`: include BrowserLink nel progetto.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

`--no-https`: il progetto non richiede HTTPS. `app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`. Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.

**page**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la pagina senza un PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

**console, angular, react, reactredux**

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**classlib**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard. Il valore predefinito è `netstandard2.0`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**mstest, xunit**

`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.

**web**

`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C` o `SingleOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. I valori possibili sono:

- `None`: nessuna autenticazione (valore predefinito).
- `Individual`: autenticazione singola.
- `IndividualB2C`: singola autenticazione con Azure AD B2C.
- `SingleOrg`: autenticazione aziendale per un singolo tenant.
- `MultiOrg`: autenticazione aziendale per più tenant.
- `Windows`: autenticazione di Windows.

`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi. Usare con l'autenticazione `IndividualB2C`. Il valore predefinito è `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto. Usare con l'autenticazione `IndividualB2C`.

`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi. Usare con l'autenticazione `SingleOrg` o `MultiOrg`. Il valore predefinito è `https://login.microsoftonline.com/`.

`--client-id <ID>`: ID client per il progetto. Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`. Il valore predefinito è `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: il dominio per il tenant della directory. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `qualified.domain.name`.

`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi. Usare con l'autenticazione `SingleOrg`. Il valore predefinito è `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento. Usare con l'autenticazione `SingleOrg` o `IndividualB2C`. Il valore predefinito è `/signin-oidc`.

`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory. Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.

`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.

`--use-browserlink`: include BrowserLink nel progetto.

`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite. Si applica solo all'autenticazione `Individual` o `IndividualB2C`.

`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.

**page**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la pagina senza un PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato. Il valore predefinito è `MyApp.Namespace`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**console, xunit, mstest, web, webapi**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp1.0` o `netcoreapp1.1`. Il valore predefinito è `netcoreapp1.0`.

**classlib**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`. Il valore predefinito è `netstandard1.4`.

**mvc**

`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione. Valori: `netcoreapp1.0` o `netcoreapp1.1`. Il valore predefinito è `netcoreapp1.0`.

`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare. Valori: `None` o `Individual`. Il valore predefinito è `None`.

`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite. Valori: `true` o `false`. Il valore predefinito è `false`.

---

## <a name="examples"></a>Esempi

Creare un progetto di applicazione console C# specificando il nome del modello:

`dotnet new "Console Application"`

Creare un progetto di applicazione console F# nella directory corrente:

`dotnet new console -lang F#`

Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:

`dotnet new classlib -lang VB -o MyLibrary`

Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:

`dotnet new mvc -au None`

Creare un nuovo progetto xUnit:

`dotnet new xunit`

Elencare tutti i modelli disponibili per MVC:

`dotnet new mvc -l`

Elencare tutti i modelli corrispondenti alla sottostringa *we*. La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.

`dotnet new we -l`

Provare a richiamare il modello corrispondente a *ng*. Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.

`dotnet new ng`

Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a>Vedere anche

- [Modelli personalizzati per dotnet new](custom-templates.md)
- [Creare un modello personalizzato per dotnet new](../tutorials/create-custom-template.md)
- [Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Modelli disponibili per dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
