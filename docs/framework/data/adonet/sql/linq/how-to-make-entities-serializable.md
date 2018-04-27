---
title: 'Procedura: rendere serializzabili le entità'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b14738e5220810f01b555e54efaad8d8898b7e45
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-make-entities-serializable"></a>Procedura: rendere serializzabili le entità
Quando si genera il codice, è possibile rendere serializzabili le entità. Le classi di entità vengono decorate con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> e le colonne con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per questo scopo.  
  
 Se si utilizza lo strumento da riga di comando SQLMetal, usare il **/serialization** con il `unidirectional` argomento. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 Le righe di comando SQLMetal seguenti consentono di produrre file con entità serializzabili.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Serializzazione](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
