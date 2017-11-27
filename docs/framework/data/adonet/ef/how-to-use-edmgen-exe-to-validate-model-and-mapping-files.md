---
title: 'Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 502646236d08198663b072a4adbbefb7376a6486
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping
In questo argomento viene illustrato come utilizzare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) strumento per convalidare il modello e i file di mapping. Per ulteriori informazioni, vedere [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Per convalidare il modello School usando EdmGen.exe  
  
1.  Creare il database School. Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Generare il modello School. Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Strumenti di ADO.NET Entity Data Model](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [Procedura: generare in anticipo visualizzazioni per migliorare le prestazioni delle Query](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Procedura: utilizzare EdmGen.exe per generare il codice di livello oggetti](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
