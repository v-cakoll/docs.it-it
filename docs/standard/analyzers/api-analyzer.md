---
title: Analizzatore di API .NET
description: Informazioni su come l'analizzatore di API .NET consente di rilevare API deprecate e problemi di compatibilità della piattaforma.
author: oliag
ms.date: 04/26/2019
ms.technology: dotnet-standard
ms.openlocfilehash: efbfa89f431bd02cdf86b8eff8704aec63a29b6c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124247"
---
# <a name="net-api-analyzer"></a>Analizzatore di API .NET

L'analizzatore di API .NET è un analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# su piattaforme diverse e rileva le chiamate alle API deprecate. Può essere utile per tutti gli sviluppatori C# in qualsiasi fase dello sviluppo.

L'analizzatore di API è disponibile come pacchetto NuGet [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/). Dopo aver impostato un riferimento in un progetto, l'analizzatore esegue automaticamente il monitoraggio del codice e segnala utilizzi problematici delle API. È anche possibile ottenere suggerimenti sulle possibili correzioni facendo clic sulla lampadina. Il menu a discesa include un'opzione per eliminare gli avvisi.

> [!NOTE]
> L'analizzatore di API .NET è ancora una versione non definitiva.

## <a name="prerequisites"></a>Prerequisites

- Visual Studio 2017 e versioni successive o Visual Studio per Mac (tutte le versioni).

## <a name="discovering-deprecated-apis"></a>Individuazione di API deprecate

### <a name="what-are-deprecated-apis"></a>Cosa sono le API deprecate?

La famiglia .NET è un set di prodotti di grandi dimensioni che vengono aggiornati costantemente per soddisfare al meglio le esigenze dei clienti. È naturale che alcune API vengano deprecate e sostituite con nuove. Un'API viene considerata deprecata quando esiste un'alternativa migliore. Un modo per segnalare che un'API è deprecata e non deve essere usata consiste nel contrassegnarla con l'attributo <xref:System.ObsoleteAttribute>. Lo svantaggio di questo approccio è che esiste un solo ID di diagnostica per tutte le API obsolete (per C#, [CS0612](../../csharp/misc/cs0612.md)). Ciò significa che:

- Non è possibile avere documenti dedicati per ogni caso.
- Non è possibile eliminare specifiche categorie di avvisi. È possibile eliminarli tutti o non eliminarli affatto.
- Per informare gli utenti di un nuovo elemento deprecato, occorre aggiornare un assembly di riferimento o un pacchetto di destinazione.

L'analizzatore di API usa codici di errore specifici dell'API che iniziano con DE (acronimo di Deprecation Errore, ovvero errore di deprecazione), che consente di controllare la visualizzazione dei singoli avvisi. Le API deprecate identificate dall'analizzatore sono definite nel repository [dotnet/platform-compat](https://github.com/dotnet/platform-compat).

### <a name="using-the-api-analyzer"></a>Uso dell'analizzatore di API

Quando un'API deprecata, ad esempio <xref:System.Net.WebClient>, viene usata nel codice, l'analizzatore di API la evidenzia con una riga ondulata verde. Quando si passa il mouse sulla chiamata dell'API viene visualizzata una lampadina con informazioni sulla deprecazione dell'API, come nell'esempio seguente:

!["Screenshot dell'API WebClient API con sottolineatura ondulata verde e lampadina a sinistra"](media/api-analyzer/green-squiggle.jpg)

La finestra **Elenco errori** contiene avvisi con un ID univoco per ogni API deprecata, come illustrato nell'esempio seguente (`DE004`): 

!["Screenshot della finestra di Elenco errori che mostra l'ID e la descrizione dell'avviso"](media/api-analyzer/warnings-id-and-descriptions.jpg "Elenco errori finestra che include avvisi.")

Facendo clic sull'ID si passa a una pagina Web con informazioni dettagliate sul motivo per cui l'API è stata deprecata e suggerimenti per le API alternative utilizzabili.

Tutti gli avvisi possono essere eliminati facendo clic con il pulsante destro del mouse sul membro evidenziato e scegliendo **Elimina \<ID diagnostica>** . Esistono due modi per eliminare gli avvisi: 

- [in locale (nell'origine)](#suppressing-warnings-locally)
- [a livello globale (in un file di eliminazione)](#suppressing-warnings-globally) - scelta consigliata

### <a name="suppressing-warnings-locally"></a>Eliminazione di avvisi in locale

Per eliminare gli avvisi in locale, fare clic con il pulsante destro del mouse sul membro per cui si vogliono eliminare gli avvisi e quindi scegliere **Azioni rapide e refactoring** > **Elimina *ID diagnostica*\<ID diagnostica>**  > **nell'origine**. La direttiva del preprocessore [#pragma warning](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) viene aggiunta al codice sorgente nell'ambito definito: !["Screenshot di codice evidenziato con #pragma warning disable"](media/api-analyzer/suppress-in-source.jpg)

### <a name="suppressing-warnings-globally"></a>Eliminazione di avvisi a livello globale

Per eliminare gli avvisi a livello globale, fare clic con il pulsante destro del mouse sul membro per cui si vogliono eliminare gli avvisi e quindi scegliere **Azioni rapide e refactoring** > **Elimina *ID diagnostica*\<ID diagnostica>**  > **nel file di eliminazione**.

!["Screenshot dell'API WebClient API con sottolineatura ondulata verde e lampadina a sinistra"](media/api-analyzer/suppress-in-sup-file.jpg)

Viene aggiunto un file *GlobalSuppressions.cs* al progetto dopo la prima eliminazione. Le ulteriori eliminazioni globali vengono aggiunte a questo file.

!["Screenshot dell'API WebClient API con sottolineatura ondulata verde e lampadina a sinistra"](media/api-analyzer/suppression-file.jpg)

L'eliminazione globale è il modo consigliato per garantire la coerenza di utilizzo delle API tra progetti.

## <a name="discovering-cross-platform-issues"></a>Individuazione dei problemi relativi alle API multipiattaforma

Come per le API deprecate, l'analizzatore identifica tutte le API che non sono multipiattaforma. Ad esempio, <xref:System.Console.WindowWidth?displayProperty=nameWithType> funziona in Windows, ma non in Linux e macOS. L'ID di diagnostica viene visualizzato nella finestra **Elenco errori**. Per eliminare l'avviso, è possibile fare clic con il pulsante destro del mouse e scegliere **Azioni rapide e refactoring**. Diversamente dai casi di deprecazione per i quali sono disponibili due opzioni (continuare a usare il membro deprecato ed eliminare gli avvisi oppure non usarlo affatto), se si sviluppa codice solo per determinate piattaforme, è possibile eliminare tutti gli avvisi per tutte le altre piattaforme in cui non si prevede di eseguire il codice. A tale scopo, è sufficiente modificare il file di progetto e aggiungere la proprietà `PlatformCompatIgnore` che elenca tutte le piattaforme da ignorare. I valori accettati sono `Linux`, `macOS` e `Windows`.

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

Se il codice è destinato a più piattaforme e si vuole avvalersi di un'API non supportata in alcune di esse, è possibile proteggere tale parte del codice con un'istruzione `if`:

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

È anche possibile usare la compilazione condizionale per ogni framework/sistema operativo di destinazione, ma attualmente è necessario eseguire questa operazione [manualmente](../frameworks.md#how-to-specify-target-frameworks).

## <a name="supported-diagnostics"></a>Diagnostica supportata

Attualmente, l'analizzatore gestisce i casi seguenti:

- Utilizzo di un'API .NET Standard che genera <xref:System.PlatformNotSupportedException> (PC001).
- Utilizzo di un'API .NET Standard non disponibile in .NET Framework 4.6.1 (PC002).
- Utilizzo di un'API nativa che non esiste nella piattaforma UWP (PC003).
- Uso delle API Delegate.BeginInvoke e EndInvoke (PC004).
- Utilizzo di un'API che è contrassegnata come deprecata (DEXXXX).

## <a name="ci-machine"></a>Server CI

Tutti questi dati diagnostici non sono disponibili solo nell'IDE, ma anche nella riga di comando come parte della compilazione del progetto, che include il server CI.

## <a name="configuration"></a>Configurazione

L'utente decide come devono essere gestiti i dati diagnostici, ovvero come avvisi, errori o suggerimenti oppure se devono essere disattivati. Ad esempio, un progettista può decidere che i problemi di compatibilità devono essere considerati come errori, che le chiamate ad alcune API devono generare avvisi, mentre altre devono generare solo suggerimenti. Queste configurazioni possono essere effettuate separatamente in base all'ID di diagnostica e al progetto. Per eseguire questa operazione, in **Esplora soluzioni** passare al nodo **Dipendenze** nel progetto. Espandere i nodi **Dipendenze** > **Analizzatori** > **Microsoft.DotNet.Analyzers.Compatibility**. Fare clic con il pulsante destro del mouse sull'ID di diagnostica, scegliere **Imposta gravità set di regole** e selezionare l'opzione desiderata.

!["Screenshot di Esplora soluzioni che mostra i dati di diagnostica e la finestra di dialogo popup con la gravità del set di regole"](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a>Vedere anche

- Post di blog [Introducing API Analyzer](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/) (Introduzione all'analizzatore di API).
- Video dimostrativo sull'[analizzatore di API](https://youtu.be/eeBEahYXGd0) su YouTube.
