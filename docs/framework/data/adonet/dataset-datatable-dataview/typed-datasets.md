---
title: Dataset tipizzati
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 7c8111e0e62a57b6745a5ea0387fc65a05839df8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785846"
---
# <a name="typed-datasets"></a><span data-ttu-id="a630b-102">Dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="a630b-102">Typed DataSets</span></span>
<span data-ttu-id="a630b-103">Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="a630b-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="a630b-104">È possibile accedere alle tabelle e alle colonne che fanno parte del **set di dati** utilizzando nomi descrittivi e variabili fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="a630b-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="a630b-105">Un **DataSet** tipizzato è una classe che deriva da un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="a630b-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="a630b-106">Di conseguenza, eredita tutti i metodi, gli eventi e le proprietà di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="a630b-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="a630b-107">Un **set di dati** tipizzato fornisce inoltre metodi, eventi e proprietà fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="a630b-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="a630b-108">È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a630b-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="a630b-109">Oltre alla migliore leggibilità del codice, un **set di dati** tipizzato consente anche all'editor di codice di Visual Studio .NET di completare automaticamente le righe durante la digitazione.</span><span class="sxs-lookup"><span data-stu-id="a630b-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="a630b-110">Il **set di dati** fortemente tipizzato fornisce inoltre l'accesso ai valori come tipo corretto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a630b-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="a630b-111">Con un set di **dati**fortemente tipizzato, vengono rilevati errori di mancata corrispondenza dei tipi quando il codice viene compilato anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a630b-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a630b-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a630b-112">In This Section</span></span>  
 [<span data-ttu-id="a630b-113">Generazione di oggetti DataSet fortemente tipizzati</span><span class="sxs-lookup"><span data-stu-id="a630b-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="a630b-114">Viene descritto come creare e utilizzare un set di **dati**fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="a630b-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="a630b-115">Annotazione di oggetti DataSet tipizzati</span><span class="sxs-lookup"><span data-stu-id="a630b-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="a630b-116">Viene descritto come aggiungere annotazioni allo schema XSD (XML Schema Definition Language) utilizzato per generare un **DataSet**fortemente tipizzato, in modo da assegnare agli elementi del **set di dati** nomi descrittivi senza modificare lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="a630b-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a630b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a630b-117">See also</span></span>

- [<span data-ttu-id="a630b-118">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="a630b-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a630b-119">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a630b-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
