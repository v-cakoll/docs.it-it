---
title: 'Procedura: definire file di modello e di mapping come risorse incorporate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 60c17ebbdd4b7e7f460855d4888a922da9c953d2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Procedura: definire file di modello e di mapping come risorse incorporate
Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] consente di distribuire i file di modello e mapping come risorse incorporate di un'applicazione. L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità. Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione). Gli strumenti [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incorporano i file di modello e di mapping per impostazione predefinita. Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme all'applicazione [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.  
  
### <a name="to-embed-model-and-mapping-files"></a>Per incorporare i file di modello e di mapping  
  
1.  In **Esplora**, selezionare il file concettuale (CSDL).  
  
2.  Nel **proprietà** riquadro, impostare **azione di compilazione** a **risorsa incorporata**.  
  
3.  Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).  
  
4.  In **Esplora**, doppio clic sul file app. config e quindi modificare il `Metadata` parametro il `connectionString` attributo basato su uno dei formati seguenti:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione).  
  
## <a name="example"></a>Esempio  
 Stringa di connessione seguente fa riferimento a modello incorporato e i file di mapping per il [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Questa stringa di connessione è archiviata nel file App.config del progetto.  
  
  
  
## <a name="see-also"></a>Vedere anche  
 [Modellazione e mapping](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Procedura: Definire la stringa di connessione](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [Procedura: Compilare una stringa di connessione EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [Strumenti di ADO.NET Entity Data Model](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
