---
title: Creazione del modello a oggetti
ms.date: 03/30/2017
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
ms.openlocfilehash: 7724d6e75b350e5c57f090d42ef1f49c4d3593b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032443"
---
# <a name="creating-the-object-model"></a><span data-ttu-id="d32d0-102">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="d32d0-102">Creating the Object Model</span></span>
<span data-ttu-id="d32d0-103">È possibile creare un modello a oggetti da un database esistente e usare il modello nello stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="d32d0-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="d32d0-104">È anche possibile personalizzare molti aspetti del modello e il relativo comportamento.</span><span class="sxs-lookup"><span data-stu-id="d32d0-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="d32d0-105">Se si usa Visual Studio, è possibile usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d32d0-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d32d0-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d32d0-106">In This Section</span></span>  
 [<span data-ttu-id="d32d0-107">Procedura: Generare il modello a oggetti in Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="d32d0-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="d32d0-108">Viene descritto come usare lo strumento SQLMetal dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d32d0-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="d32d0-109">Include anche un collegamento per il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] agli utenti di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d32d0-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="d32d0-110">Procedura: Generare il modello a oggetti come File esterno</span><span class="sxs-lookup"><span data-stu-id="d32d0-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="d32d0-111">Viene descritto come generare un file di mapping esterno anziché usare il mapping basato su attributi.</span><span class="sxs-lookup"><span data-stu-id="d32d0-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="d32d0-112">Procedura: Generare codice personalizzato modificando un File DBML</span><span class="sxs-lookup"><span data-stu-id="d32d0-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="d32d0-113">Viene descritto come generare Visual Basic o C# codice da un file di metadati DBML.</span><span class="sxs-lookup"><span data-stu-id="d32d0-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="d32d0-114">Procedura: Convalidare i file di Mapping esterni e DBML</span><span class="sxs-lookup"><span data-stu-id="d32d0-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="d32d0-115">Viene descritto come convalidare file di mapping modificati (funzionalità avanzate).</span><span class="sxs-lookup"><span data-stu-id="d32d0-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="d32d0-116">Procedura: Rendere serializzabili le entità</span><span class="sxs-lookup"><span data-stu-id="d32d0-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="d32d0-117">Viene descritto come aggiungere attributi appropriati per creare entità serializzabili.</span><span class="sxs-lookup"><span data-stu-id="d32d0-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="d32d0-118">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="d32d0-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="d32d0-119">Viene descritto come usare l'editor di codice per scrivere codice di mapping o per personalizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="d32d0-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d32d0-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d32d0-120">Related Sections</span></span>  
 [<span data-ttu-id="d32d0-121">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d32d0-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="d32d0-122">Vengono forniti dettagli sul [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d32d0-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="d32d0-123">Passaggi tipici per l'utilizzo di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d32d0-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="d32d0-124">Vengono illustrati i passaggi tipici che è necessario seguire per implementare un'applicazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d32d0-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
