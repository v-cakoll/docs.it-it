---
title: Creazione del modello a oggetti
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8686b46545699ab8c07b5d3b5f3ea26080261036
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="creating-the-object-model"></a><span data-ttu-id="8b707-102">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="8b707-102">Creating the Object Model</span></span>
<span data-ttu-id="8b707-103">È possibile creare un modello a oggetti da un database esistente e usare il modello nello stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="8b707-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="8b707-104">È anche possibile personalizzare molti aspetti del modello e il relativo comportamento.</span><span class="sxs-lookup"><span data-stu-id="8b707-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="8b707-105">Se si utilizza Visual Studio, è possibile utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="8b707-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b707-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8b707-106">In This Section</span></span>  
 [<span data-ttu-id="8b707-107">Procedura: Generare il modello a oggetti in Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="8b707-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="8b707-108">Viene descritto come usare lo strumento SQLMetal dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8b707-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="8b707-109">Fornisce inoltre un collegamento per il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per gli utenti di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8b707-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="8b707-110">Procedura: generare il modello a oggetti come file esterno</span><span class="sxs-lookup"><span data-stu-id="8b707-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="8b707-111">Viene descritto come generare un file di mapping esterno anziché usare il mapping basato su attributi.</span><span class="sxs-lookup"><span data-stu-id="8b707-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="8b707-112">Procedura: generare codice personalizzato modificando un file DBML</span><span class="sxs-lookup"><span data-stu-id="8b707-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="8b707-113">Viene descritto come generare il codice Visual Basic o c# da un file di metadati DBML.</span><span class="sxs-lookup"><span data-stu-id="8b707-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="8b707-114">Procedura: convalidare file di mapping esterni e DBML</span><span class="sxs-lookup"><span data-stu-id="8b707-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="8b707-115">Viene descritto come convalidare file di mapping modificati (funzionalità avanzate).</span><span class="sxs-lookup"><span data-stu-id="8b707-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="8b707-116">Procedura: rendere serializzabili le entità</span><span class="sxs-lookup"><span data-stu-id="8b707-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="8b707-117">Viene descritto come aggiungere attributi appropriati per creare entità serializzabili.</span><span class="sxs-lookup"><span data-stu-id="8b707-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="8b707-118">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="8b707-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="8b707-119">Viene descritto come usare l'editor di codice per scrivere codice di mapping o per personalizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="8b707-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b707-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8b707-120">Related Sections</span></span>  
 [<span data-ttu-id="8b707-121">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b707-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="8b707-122">Vengono fornite informazioni dettagliate sul [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="8b707-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="8b707-123">Passaggi tipici per l'utilizzo di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b707-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="8b707-124">Vengono illustrati i passaggi tipici che è necessario seguire per implementare un'applicazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b707-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
