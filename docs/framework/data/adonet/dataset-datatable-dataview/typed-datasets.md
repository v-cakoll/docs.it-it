---
title: Dataset tipizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3d5edc4f469b59ff787e500ad447fe0076c332c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="typed-datasets"></a><span data-ttu-id="95aaa-102">Dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="95aaa-102">Typed DataSets</span></span>
<span data-ttu-id="95aaa-103">Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="95aaa-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="95aaa-104">Tabelle e colonne che fanno parte di **DataSet** sono accessibili mediante nomi descrittivi e variabili fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="95aaa-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="95aaa-105">Un oggetto tipizzato **DataSet** è una classe che deriva da un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="95aaa-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="95aaa-106">In quanto tale, eredita tutti i metodi, eventi e proprietà di un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="95aaa-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="95aaa-107">Inoltre, un oggetto tipizzato **DataSet** fornisce metodi fortemente tipizzati, proprietà ed eventi.</span><span class="sxs-lookup"><span data-stu-id="95aaa-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="95aaa-108">È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="95aaa-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="95aaa-109">Oltre a una migliore leggibilità del codice, un oggetto tipizzato **DataSet** consente inoltre il codice di Visual Studio .NET editor per completare automaticamente le righe durante la digitazione.</span><span class="sxs-lookup"><span data-stu-id="95aaa-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="95aaa-110">Inoltre, l'oggetto fortemente tipizzato **DataSet** consente di accedere ai valori del tipo corretto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95aaa-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="95aaa-111">Con un oggetto fortemente tipizzato **DataSet**, gli errori di mancata corrispondenza di tipo vengono rilevati quando il codice viene compilato, anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95aaa-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95aaa-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="95aaa-112">In This Section</span></span>  
 [<span data-ttu-id="95aaa-113">Generazione di DataSet fortemente tipizzati</span><span class="sxs-lookup"><span data-stu-id="95aaa-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="95aaa-114">Viene descritto come creare e usare un oggetto fortemente tipizzato **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="95aaa-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="95aaa-115">Annotazione di dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="95aaa-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="95aaa-116">Viene descritto come annotare lo schema XML Schema definition language (XSD) utilizzato per generare un oggetto fortemente tipizzato **DataSet**per assegnare **DataSet** nomi descrittivi di elementi senza alterare lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="95aaa-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95aaa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95aaa-117">See Also</span></span>  
 [<span data-ttu-id="95aaa-118">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="95aaa-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="95aaa-119">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="95aaa-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
