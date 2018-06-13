---
title: Modellazione e mapping
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 88c8786a5e538d8441e03e46e59743e4c489b4c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762936"
---
# <a name="modeling-and-mapping"></a>Modellazione e mapping
In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è possibile definire il modello concettuale, il modello di archiviazione e il mapping tra i due nella modalità che soddisfa meglio le esigenze dell'applicazione. Strumenti di Entity Data Model in Visual Studio consentono di creare una. [file edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) da un database o un modello grafico e quindi aggiornare file quando viene modificata del database o del modello.  
  
 A partire da Entity Framework 4.1 è inoltre possibile creare un modello a livello di codice usando lo sviluppo Code First. Esistono due scenari diversi per lo sviluppo Code First. In entrambi i casi, lo sviluppatore definisce un modello codificando le definizioni di classi di .NET Framework e, successivamente, in modo facoltativo specifica la configurazione o il mapping aggiuntivo usando le annotazioni dei dati o l'API Fluent.  
  
 Per ulteriori informazioni, vedere [la creazione e il Mapping di un modello concettuale](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 È inoltre possibile utilizzare il generatore di EDM, incluso il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. EdmGen.exe genera file con estensione csdl, ssdl e msl da un'origine dati esistente. È possibile inoltre creare il contenuto del modello e del mapping manualmente. Per ulteriori informazioni, vedere [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).
