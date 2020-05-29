---
title: Collegamento all'origine e librerie .NET
description: Procedure consigliate per l'uso del collegamento all'origine per migliorare il debug per le librerie .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 5dee2a6b1f77daa641351e02c1dd3e0a38f66550
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201974"
---
# <a name="source-link"></a>Collegamento all'origine

Il collegamento all'origine è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet da parte degli sviluppatori. Il collegamento all'origine viene eseguito durante la creazione del pacchetto NuGet e incorpora i metadati di controllo del codice sorgente all'interno degli assembly e del pacchetto. Gli sviluppatori che scaricano il pacchetto e che hanno abilitato il collegamento all'origine in Visual Studio possono eseguire istruzione per istruzione il relativo codice sorgente. Il collegamento all'origine fornisce i metadati di controllo del codice sorgente per creare una straordinaria esperienza di debug.

## <a name="source-link-demo"></a>Demo del collegamento all'origine

<!--markdownlint-disable MD034 -->
> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a>Uso del collegamento all'origine

Le istruzioni per l'uso del collegamento all'origine sono reperibili nel repository GitHub [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).

È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati di collegamento all'origine siano stati incorporati correttamente nel pacchetto. Controllare `Repository` che i metadati siano presenti con un identificatore di commit e che i file con estensione PDB si trovino con la dll di ogni destinazione.

![Collegamento all'origine in Esplora pacchetti NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "Collegamento all'origine in Esplora pacchetti NuGet")

✔️ VALUTARE l'uso del collegamento all'origine per aggiungere metadati di controllo del codice sorgente agli assembly e ai pacchetti NuGet.

> [!TIP]
> È possibile migliorare ulteriormente l'esperienza di debug di uno sviluppatore tramite l'aggiunta di attributi del debugger ai tipi in uso.
>
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> può personalizzare la modalità di visualizzazione di una classe o di un campo nelle finestre delle variabili del debugger.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al debugger di eseguire il codice un'istruzione alla volta anziché eseguire un'istruzione nel codice.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> controlla se viene visualizzato un membro nelle finestre delle variabili del debugger.

✔️ VALUTARE la pubblicazione dei file di simboli (`*.pdb`).

> Per ottenere un'esperienza di debug ottimale, la libreria deve pubblicare i file di simboli oltre a usare il collegamento all'origine. Per altre informazioni sui file di simboli e i pacchetti di simboli, vedere [Pacchetti di simboli](./nuget.md#symbol-packages).

✔️ CONSIGLIABILE abilitare le compilazioni deterministiche.

> Le compilazioni deterministiche consentono di verificare che il file binario risultante sia stato compilato dall'origine specificata e fornisca la tracciabilità. Per ulteriori informazioni sulle compilazioni deterministiche e istruzioni per abilitarle, vedere [compilazioni deterministiche](https://github.com/clairernovotny/DeterministicBuilds).

>[!div class="step-by-step"]
>[Precedente](dependencies.md) 
> [Avanti](publish-nuget-package.md)
