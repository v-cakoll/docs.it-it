---
title: Stored procedure CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d2fde4fdcd5ab63906256d814256578b9baa9ecd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782502"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="af6c3-102">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="af6c3-102">CLR Stored Procedures</span></span>
<span data-ttu-id="af6c3-103">Le stored procedure sono routine che non possono essere usate in espressioni scalari.</span><span class="sxs-lookup"><span data-stu-id="af6c3-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="af6c3-104">Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.</span><span class="sxs-lookup"><span data-stu-id="af6c3-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af6c3-105">In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="af6c3-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="af6c3-106">È necessario specificare per passare il parametro per riferimento e applicare l' \<attributo out () > per rappresentare un parametro di output, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="af6c3-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="af6c3-107">Per informazioni più dettagliate, vedere la versione di [SQL Server documentazione](/sql) per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="af6c3-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="af6c3-108">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="af6c3-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="af6c3-109">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="af6c3-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="af6c3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af6c3-110">See also</span></span>

- <span data-ttu-id="af6c3-111">[Creazione di oggetti SQL Server 2005 nel codice gestito](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="af6c3-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="af6c3-112">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="af6c3-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
