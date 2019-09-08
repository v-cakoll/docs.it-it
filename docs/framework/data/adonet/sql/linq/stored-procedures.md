---
title: Stored procedure
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 80ea105eef33ebb2a0e52d91a631258400ea3dff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792485"
---
# <a name="stored-procedures"></a><span data-ttu-id="cab93-102">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="cab93-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="cab93-103">utilizza i metodi nel modello a oggetti per rappresentare le stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="cab93-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="cab93-104">Per definire metodi come stored procedure, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cab93-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="cab93-105">Per ulteriori informazioni, vedere [il modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="cab93-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="cab93-106">Gli sviluppatori che usano Visual Studio utilizzeranno in genere il Object Relational Designer per eseguire il mapping delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cab93-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="cab93-107">Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cab93-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cab93-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cab93-108">In This Section</span></span>  
 [<span data-ttu-id="cab93-109">Procedura: Restituisci set di righe</span><span class="sxs-lookup"><span data-stu-id="cab93-109">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="cab93-110">Viene descritto come restituire righe di dati e viene illustrato come usare un parametro di input.</span><span class="sxs-lookup"><span data-stu-id="cab93-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="cab93-111">Procedura: Utilizzare stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="cab93-111">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="cab93-112">Viene descritto come usare parametri di input e output.</span><span class="sxs-lookup"><span data-stu-id="cab93-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="cab93-113">Procedura: Utilizzare stored procedure mappate per più forme di risultati</span><span class="sxs-lookup"><span data-stu-id="cab93-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="cab93-114">Viene descritto come ottenere la restituzione di più forme nella stessa stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cab93-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="cab93-115">Procedura: Utilizzare stored procedure mappate per forme di risultati sequenziali</span><span class="sxs-lookup"><span data-stu-id="cab93-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="cab93-116">Viene descritto come ottenere più forme dove la sequenza restituita è nota.</span><span class="sxs-lookup"><span data-stu-id="cab93-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="cab93-117">Personalizzazione di operazioni utilizzando stored procedure</span><span class="sxs-lookup"><span data-stu-id="cab93-117">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="cab93-118">Viene descritto come usare stored procedure per implementare operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cab93-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="cab93-119">Personalizzazione di operazioni utilizzando esclusivamente stored procedure</span><span class="sxs-lookup"><span data-stu-id="cab93-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="cab93-120">Viene descritto come usare unicamente stored procedure per implementare operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cab93-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cab93-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cab93-121">Related Sections</span></span>  
 [<span data-ttu-id="cab93-122">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="cab93-122">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="cab93-123">Fornisce informazioni sulla creazione e sull'uso del modello a oggetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cab93-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="cab93-124">Procedura dettagliata: Utilizzo solo di stored procedure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab93-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="cab93-125">Sono incluse procedure che illustrano come usare stored procedure in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cab93-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="cab93-126">Procedura dettagliata: Utilizzo solo di stored procedureC#()</span><span class="sxs-lookup"><span data-stu-id="cab93-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="cab93-127">Sono incluse procedure che illustrano come usare stored procedure in C#.</span><span class="sxs-lookup"><span data-stu-id="cab93-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
