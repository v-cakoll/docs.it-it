---
title: Stored procedure CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: df323e2d1b50dcd1b2087141deefa1c86723b346
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930112"
---
# <a name="clr-stored-procedures"></a>Stored procedure CLR
Le stored procedure sono routine che non possono essere usate in espressioni scalari. Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.  
  
> [!NOTE]
>  In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#. È necessario specificare per passare il parametro per riferimento e applicare il \<out () > attributo per rappresentare un parametro di output, come illustrato di seguito:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Per informazioni più dettagliate, vedere la versione di [documentazione di SQL Server](/sql) per la versione di SQL Server in uso.
  
 **Documentazione di SQL Server**

1. [Stored procedure CLR](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di oggetti di SQL Server 2005 nel codice gestito](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
