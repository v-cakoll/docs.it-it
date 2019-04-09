---
title: Stored procedure CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230811"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="d4de2-102">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d4de2-102">CLR Stored Procedures</span></span>
<span data-ttu-id="d4de2-103">Le stored procedure sono routine che non possono essere usate in espressioni scalari.</span><span class="sxs-lookup"><span data-stu-id="d4de2-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="d4de2-104">Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.</span><span class="sxs-lookup"><span data-stu-id="d4de2-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4de2-105">In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d4de2-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="d4de2-106">È necessario specificare per passare il parametro per riferimento e applicare il \<out () > attributo per rappresentare un parametro di output, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d4de2-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="d4de2-107">Per informazioni più dettagliate, vedere la versione di [documentazione di SQL Server](/sql) per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="d4de2-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 **<span data-ttu-id="d4de2-108">Documentazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4de2-108">SQL Server documentation</span></span>**

1. [<span data-ttu-id="d4de2-109">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d4de2-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="d4de2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4de2-110">See also</span></span>

- [<span data-ttu-id="d4de2-111">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="d4de2-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [<span data-ttu-id="d4de2-112">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d4de2-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
