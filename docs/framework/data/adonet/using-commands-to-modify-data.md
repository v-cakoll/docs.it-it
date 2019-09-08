---
title: Utilizzo di comandi per modificare i dati
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780568"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="50b13-102">Utilizzo di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="50b13-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="50b13-103">Con un provider di dati .NET Framework è possibile eseguire stored procedure o istruzioni DDL (Data Definition Language), ad esempio CREATE TABLE e ALTER COLUMN, per modificare lo schema di un database o di un catalogo.</span><span class="sxs-lookup"><span data-stu-id="50b13-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="50b13-104">Questi comandi non restituiscono righe come query, quindi l'oggetto **Command** fornisce un **ExecuteNonQuery** per elaborarli.</span><span class="sxs-lookup"><span data-stu-id="50b13-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="50b13-105">Oltre a usare **ExecuteNonQuery** per modificare lo schema, è anche possibile usare questo metodo per elaborare istruzioni SQL che modificano i dati ma che non restituiscono righe, ad esempio INSERT, Update e DELETE.</span><span class="sxs-lookup"><span data-stu-id="50b13-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="50b13-106">Anche se le righe non vengono restituite dal metodo **ExecuteNonQuery** , i parametri di input e di output e i valori restituiti possono essere passati e restituiti tramite la raccolta **Parameters** dell'oggetto **Command** .</span><span class="sxs-lookup"><span data-stu-id="50b13-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50b13-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="50b13-107">In This Section</span></span>  
 [<span data-ttu-id="50b13-108">Aggiornamento di dati in un'origine dati</span><span class="sxs-lookup"><span data-stu-id="50b13-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="50b13-109">Viene descritto come eseguire i comandi o le stored procedure che modificano i dati in un database.</span><span class="sxs-lookup"><span data-stu-id="50b13-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="50b13-110">Esecuzione di operazioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="50b13-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="50b13-111">Viene descritto come eseguire i comandi per la modifica dello schema di database.</span><span class="sxs-lookup"><span data-stu-id="50b13-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b13-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50b13-112">See also</span></span>

- [<span data-ttu-id="50b13-113">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50b13-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="50b13-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="50b13-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="50b13-115">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50b13-115">ADO.NET Overview</span></span>](ado-net-overview.md)
