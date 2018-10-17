---
title: Librerie SourceLink e .NET
description: Procedure consigliate per l'uso SourceLink per migliorare il debug per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370044"
---
# <a name="sourcelink"></a>SourceLink

SourceLink è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet dagli sviluppatori. SourceLink esegue quando si crea il pacchetto NuGet e incorpora i metadati di controllo di origine all'interno di assembly e il pacchetto. Gli sviluppatori che scarica il pacchetto e avere SourceLink abilitato in Visual Studio possono eseguirne il relativo codice sorgente. SourceLink fornisce i metadati di controllo di origine per creare una straordinaria esperienza di debug.

## <a name="sourcelink-demo"></a>Demo SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Usando SourceLink

Istruzioni per l'uso SourceLink sono reperibile nella [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) repository GitHub.

È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati SourceLink sono stato incorporato nel pacchetto. Controllare il `Repository` metadati sono presenti con un identificatore di commento e che si trovano con. dll del ogni destinazione file con estensione pdb.

![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")

**Provare a ✔️** usando SourceLink per aggiungere metadati di controllo di origine per l'assembly e il pacchetto NuGet.

**Provare a ✔️** inclusi i file PDB nel pacchetto NuGet.

>[!div class="step-by-step"]
[Precedente](./dependencies.md)
[Successivo](./publish-nuget-package.md)
