---
title: Utilizzo di comandi per modificare i dati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 70a83453eef990a03515a4860917f3c4d72599c3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="550c1-102">Utilizzo di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="550c1-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="550c1-103">Con un provider di dati .NET Framework è possibile eseguire stored procedure o istruzioni DDL (Data Definition Language), ad esempio CREATE TABLE e ALTER COLUMN, per modificare lo schema di un database o di un catalogo.</span><span class="sxs-lookup"><span data-stu-id="550c1-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="550c1-104">Questi comandi non restituiscono righe come una query, pertanto la **comando** oggetto fornisce un **ExecuteNonQuery** per elaborarli.</span><span class="sxs-lookup"><span data-stu-id="550c1-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="550c1-105">Oltre a utilizzare **ExecuteNonQuery** per modificare lo schema, è inoltre possibile utilizzare questo metodo per elaborare le istruzioni SQL che modificano i dati ma che non restituiscono righe, ad esempio INSERT, UPDATE e DELETE.</span><span class="sxs-lookup"><span data-stu-id="550c1-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="550c1-106">Anche se le righe non vengono restituite dal **ExecuteNonQuery** parametri di metodo di input e output e valori restituiti possono essere passati e restituiti tramite il **parametri** insieme del **comando**  oggetto.</span><span class="sxs-lookup"><span data-stu-id="550c1-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="550c1-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="550c1-107">In This Section</span></span>  
 [<span data-ttu-id="550c1-108">Aggiornamento di dati in un'origine dati</span><span class="sxs-lookup"><span data-stu-id="550c1-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="550c1-109">Viene descritto come eseguire i comandi o le stored procedure che modificano i dati in un database.</span><span class="sxs-lookup"><span data-stu-id="550c1-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="550c1-110">Esecuzione di operazioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="550c1-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="550c1-111">Viene descritto come eseguire i comandi per la modifica dello schema di database.</span><span class="sxs-lookup"><span data-stu-id="550c1-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550c1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="550c1-112">See Also</span></span>  
 [<span data-ttu-id="550c1-113">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="550c1-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="550c1-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="550c1-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="550c1-115">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="550c1-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
