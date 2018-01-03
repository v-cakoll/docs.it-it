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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dfed0124c33c90427c9b888f5aa7bb191aea0400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="4709c-102">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="4709c-102">CLR Stored Procedures</span></span>
<span data-ttu-id="4709c-103">Le stored procedure sono routine che non possono essere usate in espressioni scalari.</span><span class="sxs-lookup"><span data-stu-id="4709c-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="4709c-104">Possono restituire risultati in formato schematico e messaggi al client, eseguire chiamate di istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) nonché restituire parametri di output.</span><span class="sxs-lookup"><span data-stu-id="4709c-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4709c-105">In Microsoft Visual Basic i parametri di output non sono supportati come in Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="4709c-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="4709c-106">È necessario specificare per passare il parametro per riferimento e applicare il \<out () > attributo per rappresentare un parametro di output, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4709c-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 <span data-ttu-id="4709c-107">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="4709c-107">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4709c-108">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4709c-108">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="4709c-109">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="4709c-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="4709c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4709c-110">See Also</span></span>  
 [<span data-ttu-id="4709c-111">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="4709c-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="4709c-112">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="4709c-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
