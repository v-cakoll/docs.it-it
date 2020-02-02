---
title: Distribuzione di applicazioni .NET Core
description: Informazioni sui modi per distribuire un'applicazione .NET Core.
ms.date: 12/03/2018
ms.openlocfilehash: 425f0d5bf11fd0572825d2025005aacf65d7d2cd
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920884"
---
# <a name="net-core-application-deployment"></a>Distribuzione di applicazioni .NET Core

È possibile creare tre tipi di distribuzioni per le applicazioni .NET Core:

- Distribuzione dipendente dal framework. Come suggerisce il nome, la distribuzione dipendente dal framework si basa sulla presenza di una versione condivisa a livello di sistema di .NET Core nel sistema di destinazione. Poiché .NET Core è già presente, l'app è anche portabile tra le installazioni di .NET Core. L'app contiene solo il proprio codice e le dipendenze di terze parti non sono comprese nelle librerie di .NET Core. Le distribuzioni dipendenti dal framework contengono file con estensione *dll* che possono essere avviati dalla riga di comando tramite l'[utilità dotnet](../tools/dotnet.md). Ad esempio, `dotnet app.dll` esegue un'applicazione denominata `app`.

- Distribuzione autonoma. A differenza delle distribuzioni dipendenti dal framework, una distribuzione autonoma non si basa sulla presenza dei componenti condivisi nel sistema di destinazione. Tutti i componenti, inclusi librerie e runtime di .NET Core, sono inclusi nell'applicazione e isolati dalle altre applicazioni .NET Core. Le distribuzioni autonome includono un file eseguibile (ad esempio *app.exe* su piattaforme Windows per un'applicazione denominata `app`), che è una versione ridenominata dell'host .NET Core specifico della piattaforma, e un file con estensione *dll* (ad esempio *app.dll*), che indica l'applicazione.

- File eseguibili dipendenti dal framework. Genera un file eseguibile che viene eseguito in una piattaforma di destinazione. Analogamente alle distribuzioni dipendenti dal framework, i file eseguibili dipendenti dal framework sono specifici della piattaforma e non sono autonomi. L'esecuzione di queste distribuzioni si basa ancora sulla presenza di una versione di .NET Core a livello di sistema condivisa. Diversamente da una distribuzione autonoma, l'app contiene solo il codice e le dipendenze di terze parti non sono comprese nelle librerie di .NET Core. I file eseguibili dipendenti dal framework generano un file eseguibile che viene eseguito nella piattaforma di destinazione.

## <a name="framework-dependent-deployments-fdd"></a>Distribuzioni dipendenti dal framework

Per una distribuzione dipendente dal framework, vengono distribuite solo l'app e le dipendenze di terze parti. L'app userà la versione di .NET Core presente nel sistema di destinazione. Si tratta del modello di distribuzione predefinito per le app .NET Core e ASP.NET Core destinate a .NET Core.

### <a name="why-create-a-framework-dependent-deployment"></a>Perché creare una distribuzione dipendente dal framework?

Una distribuzione dipendente dal framework offre numerosi vantaggi:

- Non è necessario definire in anticipo i sistemi operativi di destinazione in cui verrà eseguita l'app .NET Core. Poiché .NET Core usa un formato di file PE comune per gli eseguibili e le librerie indipendentemente dal sistema operativo, .NET Core può eseguire l'app indipendentemente dal sistema operativo sottostante. Per altre informazioni sul formato di file PE, vedere [.NET Assembly File Format](../../standard/assembly/file-format.md) (Formato del file di assembly .NET).

- La dimensione del pacchetto di distribuzione è ridotta. È sufficiente distribuire l'app e le relative dipendenze, non .NET Core.

- A meno che non vengano sottoposte a override, le distribuzioni dipendenti dal framework useranno l'ultimo runtime servito installato nel sistema di destinazione. In questo modo l'applicazione può usare la versione di correzione più recente del runtime di .NET Core. 

- Più app usano la stessa installazione di .NET Core, in questo modo si riduce sia lo spazio su disco sia l'utilizzo della memoria nei sistemi host.

Sono presenti anche alcuni svantaggi:

- L'app può essere eseguita solo se la versione di .NET Core specificata come destinazione dall'app [o una versione successiva](../versions/selection.md#framework-dependent-apps-roll-forward) è già installata nel sistema host.

- Nelle versioni successive è possibile che il runtime e le librerie di .NET Core vengano modificate senza notificare l'utente. In rari casi, questo scenario può comportare la modifica del comportamento dell'app.

## <a name="self-contained-deployments-scd"></a>Distribuzioni autonome

Per una distribuzione autonoma, si distribuiscono l'app e le eventuali dipendenze di terze parti richieste, insieme alla versione di .NET Core usata per compilare l'app. Poiché la creazione di una distribuzione autonoma non include le [dipendenze native di .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) su più piattaforme, queste dipendenze devono essere presenti prima di eseguire l'applicazione. Per altre informazioni sull'associazione di versioni in fase di esecuzione, vedere l'articolo sull'[associazione delle versioni in .NET Core](../versions/selection.md).

A partire da NET Core 2.1 SDK (versione 2.1.300), .NET Core supporta il *roll forward della versione della patch*. Quando si crea una distribuzione autonoma, gli strumenti di .NET Core includono automaticamente l'ultimo il runtime servito della versione di .NET Core a cui l'applicazione è destinata. Il runtime di manutenzione più recente include patch di sicurezza e altre correzioni di bug. Non è necessario che il runtime servito sia presente nel sistema di compilazione. viene scaricato automaticamente da NuGet.org. Per altre informazioni, incluse le istruzioni su come rifiutare esplicitamente il rollforward della versione patch, vedere [rollforward del runtime di distribuzione autonomo](runtime-patch-selection.md).

Le distribuzioni dipendenti dal framework e le distribuzioni autonome usano eseguibili host separati, quindi è possibile firmare un eseguibile host per una distribuzione autonoma con la firma del server di pubblicazione.

### <a name="why-deploy-a-self-contained-deployment"></a>Perché distribuire una distribuzione autonoma?

Una distribuzione autonoma offre due vantaggi principali:

- Si dispone del controllo esclusivo della versione di .NET Core che viene distribuita con l'app. .NET Core può essere usato solo dall'utente.

- È possibile garantire che il sistema di destinazione esegua l'app .NET Core, poiché viene specificata la versione di .NET Core in cui verrà eseguita.

Sono presenti anche alcuni svantaggi:

- Poiché .NET Core è incluso nel pacchetto di distribuzione, è necessario selezionare in anticipo le piattaforme di destinazione per cui vengono creati i pacchetti di distribuzione.

- La dimensione del pacchetto di distribuzione è relativamente elevata, poiché è necessario includere .NET Core, nonché l'app e le relative dipendenze di terze parti.

  A partire da .NET Core 2.0, è possibile ridurre le dimensioni della distribuzione nei sistemi Linux di circa 28 MB usando la [*modalità invariante della globalizzazione*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md). In genere, .NET Core in Linux si basa sulle [librerie ICU](http://icu-project.org) per il supporto della globalizzazione. Nella modalità invariante le librerie non sono incluse nella distribuzione e tutte le impostazioni cultura si comportano come le [impostazioni cultura inglese non dipendenti da paese/area geografica](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- La distribuzione di numerose app .NET Core autonome a un sistema comporta l'utilizzo di quantità significative di spazio su disco, poiché ogni app duplica i file di .NET Core.

## <a name="framework-dependent-executables-fde"></a>File eseguibili dipendenti dal framework

A partire da .NET Core 2.2, è possibile distribuire l'app come file eseguibile dipendente dal framework, con eventuali dipendenze di terze parti necessarie. L'app userà la versione di .NET Core installata nel sistema di destinazione.

### <a name="why-deploy-a-framework-dependent-executable"></a>Perché distribuire un file eseguibile dipendente dal framework?

Un file eseguibile dipendente dal framework offre numerosi vantaggi:

- La dimensione del pacchetto di distribuzione è ridotta. È sufficiente distribuire l'app e le relative dipendenze, non .NET Core.

- Più app usano la stessa installazione di .NET Core, in questo modo si riduce sia lo spazio su disco sia l'utilizzo della memoria nei sistemi host.

- L'app può essere eseguita chiamando il file eseguibile pubblicato senza richiamare direttamente l'utilità `dotnet`.

Sono presenti anche alcuni svantaggi:

- L'app può essere eseguita solo se la versione di .NET Core specificata come destinazione dall'app [o una versione successiva](../versions/selection.md#framework-dependent-apps-roll-forward) è già installata nel sistema host.

- Nelle versioni successive è possibile che il runtime e le librerie di .NET Core vengano modificate senza notificare l'utente. In rari casi, questo scenario può comportare la modifica del comportamento dell'app.

- È necessario pubblicare l'app per ogni piattaforma di destinazione.

## <a name="step-by-step-examples"></a>Esempi dettagliati

Per esempi dettagliati della distribuzione di app .NET Core con la interfaccia della riga di comando di .NET Core, vedere [pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](deploy-with-cli.md). Per esempi dettagliati della distribuzione di app .NET Core con Visual Studio, vedere [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Distribuzione di app .NET Core con Visual Studio). 

## <a name="see-also"></a>Vedere anche

- [Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](deploy-with-cli.md)
- [Distribuzione di app .NET Core con Visual Studio](deploy-with-vs.md)
- [Pacchetti, metapacchetti e framework](../packages.md)
- [Catalogo dei RID (Runtime IDentifier) di .NET Core](../rid-catalog.md)
