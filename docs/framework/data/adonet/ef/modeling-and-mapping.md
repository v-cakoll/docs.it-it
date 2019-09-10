---
title: Modellazione e mapping
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 133539ab1b6d6f2f0ab3f8deed5b22240c2bb07e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854400"
---
# <a name="modeling-and-mapping"></a>Modellazione e mapping
Nel Entity Framework è possibile definire il modello concettuale, il modello di archiviazione e il mapping tra i due nel modo più appropriato per l'applicazione. Gli strumenti Entity Data Model in Visual Studio consentono di creare un oggetto. [file edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) da un database o da un modello grafico e quindi aggiornare il file quando il database o il modello viene modificato.  
  
 A partire da Entity Framework 4.1 è inoltre possibile creare un modello a livello di codice usando lo sviluppo Code First. Esistono due scenari diversi per lo sviluppo Code First. In entrambi i casi, lo sviluppatore definisce un modello codificando le definizioni di classi di .NET Framework e, successivamente, in modo facoltativo specifica la configurazione o il mapping aggiuntivo usando le annotazioni dei dati o l'API Fluent.  
  
 Per ulteriori informazioni, vedere [creazione e mapping di un modello concettuale](https://go.microsoft.com/fwlink/?LinkId=235016).  
  
 È anche possibile usare il generatore EDM, incluso nel .NET Framework. EdmGen.exe genera file con estensione csdl, ssdl e msl da un'origine dati esistente. È possibile inoltre creare il contenuto del modello e del mapping manualmente. Per ulteriori informazioni, vedere [Generatore EDM (EdmGen. exe)](edm-generator-edmgen-exe.md).
