---
title: Stored procedure
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 9201965192f300de62679c1e5be75cf98a24e700
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360596"
---
# <a name="stored-procedures"></a><span data-ttu-id="96c44-102">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="96c44-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="96c44-103"> Usa i metodi nel modello a oggetti per rappresentare stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="96c44-103"> uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="96c44-104">Per definire metodi come stored procedure, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="96c44-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="96c44-105">Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="96c44-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="96c44-106">Gli sviluppatori che usano Visual Studio utilizza in genere il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="96c44-106">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="96c44-107">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="96c44-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96c44-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="96c44-108">In This Section</span></span>  
 [<span data-ttu-id="96c44-109">Procedura: restituire rowset</span><span class="sxs-lookup"><span data-stu-id="96c44-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="96c44-110">Viene descritto come restituire righe di dati e viene illustrato come usare un parametro di input.</span><span class="sxs-lookup"><span data-stu-id="96c44-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="96c44-111">Procedura: utilizzare stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="96c44-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="96c44-112">Viene descritto come usare parametri di input e output.</span><span class="sxs-lookup"><span data-stu-id="96c44-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="96c44-113">Procedura: utilizzare stored procedure mappate per più forme di risultati</span><span class="sxs-lookup"><span data-stu-id="96c44-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="96c44-114">Viene descritto come ottenere la restituzione di più forme nella stessa stored procedure.</span><span class="sxs-lookup"><span data-stu-id="96c44-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="96c44-115">Procedura: utilizzare stored procedure mappate per forme di risultati sequenziali</span><span class="sxs-lookup"><span data-stu-id="96c44-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="96c44-116">Viene descritto come ottenere più forme dove la sequenza restituita è nota.</span><span class="sxs-lookup"><span data-stu-id="96c44-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="96c44-117">Personalizzazione di operazioni utilizzando stored procedure</span><span class="sxs-lookup"><span data-stu-id="96c44-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="96c44-118">Viene descritto come usare stored procedure per implementare operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="96c44-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="96c44-119">Personalizzazione di operazioni utilizzando esclusivamente stored procedure</span><span class="sxs-lookup"><span data-stu-id="96c44-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="96c44-120">Viene descritto come usare unicamente stored procedure per implementare operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="96c44-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96c44-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="96c44-121">Related Sections</span></span>  
 [<span data-ttu-id="96c44-122">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="96c44-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="96c44-123">Fornisce informazioni sulla creazione e sull'uso del modello a oggetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c44-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="96c44-124">Procedura dettagliata: utilizzo solo di stored procedure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c44-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="96c44-125">Sono incluse procedure che illustrano come usare stored procedure in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96c44-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="96c44-126">Procedura dettagliata: utilizzo solo di stored procedure (C#)</span><span class="sxs-lookup"><span data-stu-id="96c44-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="96c44-127">Sono incluse procedure che illustrano come usare stored procedure in C#.</span><span class="sxs-lookup"><span data-stu-id="96c44-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
