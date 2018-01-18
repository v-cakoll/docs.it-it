---
title: Modellazione e mapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 82bb3ca8bd5ef0659bbb222753b3225288fcbcfc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="modeling-and-mapping"></a>Modellazione e mapping
In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è possibile definire il modello concettuale, il modello di archiviazione e il mapping tra i due nella modalità che soddisfa meglio le esigenze dell'applicazione. Gli strumenti di Entity Data Model in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] consentono di creare un.[ file edmx](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) da un database o un modello grafico e quindi aggiornare file quando viene modificato il modello o database.  
  
 A partire da Entity Framework 4.1 è inoltre possibile creare un modello a livello di codice usando lo sviluppo Code First. Esistono due scenari diversi per lo sviluppo Code First. In entrambi i casi, lo sviluppatore definisce un modello codificando le definizioni di classi di .NET Framework e, successivamente, in modo facoltativo specifica la configurazione o il mapping aggiuntivo usando le annotazioni dei dati o l'API Fluent.  
  
 Per ulteriori informazioni, vedere [la creazione e il Mapping di un modello concettuale](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 È inoltre possibile utilizzare il generatore di EDM, incluso il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. EdmGen.exe genera file con estensione csdl, ssdl e msl da un'origine dati esistente. È possibile inoltre creare il contenuto del modello e del mapping manualmente. Per ulteriori informazioni, vedere [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).
