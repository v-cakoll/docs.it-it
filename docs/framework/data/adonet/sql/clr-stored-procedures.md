---
title: Stored procedure CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: c02efa3f0a91d176b626761335bd2d5a2b96b966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917961"
---
# <a name="clr-stored-procedures"></a>Stored procedure CLR
Le stored procedure sono routine che non possono essere usate in espressioni scalari. Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.  
  
> [!NOTE]
> In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#. È necessario specificare per passare il parametro per riferimento e applicare l' \<attributo out () > per rappresentare un parametro di output, come nell'esempio seguente:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Per informazioni più dettagliate, vedere la versione di [SQL Server documentazione](/sql) per la versione di SQL Server in uso.
  
 **Documentazione di SQL Server**

1. [Stored procedure CLR](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di oggetti SQL Server 2005 nel codice gestito](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
