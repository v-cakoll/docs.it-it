---
title: Stored procedure CLR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aebc681482482c364f762b12065cf041f4976be9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="clr-stored-procedures"></a>Stored procedure CLR
Le stored procedure sono routine che non possono essere usate in espressioni scalari. Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.  
  
> [!NOTE]
>  In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#. È necessario specificare per passare il parametro per riferimento e applicare il \<out () > attributo per rappresentare un parametro di output, come illustrato di seguito:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
1.  [Stored procedure CLR](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di oggetti di SQL Server 2005 nel codice gestito](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
