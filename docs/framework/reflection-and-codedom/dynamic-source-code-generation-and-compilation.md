---
title: Generazione e compilazione dinamica di codice sorgente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 535a60aa1a174319a4db3403a64c3998784bbb58
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="85b19-102">Generazione e compilazione dinamica di codice sorgente</span><span class="sxs-lookup"><span data-stu-id="85b19-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="85b19-103">.NET Framework include un meccanismo denominato Code Document Object Model (CodeDOM) che consente agli sviluppatori di programmi che creano codice sorgente di generarlo, in fase di esecuzione, in più linguaggi di programmazione in base a un unico modello che rappresenta il codice da generare.</span><span class="sxs-lookup"><span data-stu-id="85b19-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="85b19-104">Per rappresentare il codice sorgente, gli elementi CodeDOM vengono collegati tra loro per formare una struttura di dati nota come grafico CodeDOM che modella la struttura del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="85b19-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="85b19-105">Lo spazio dei nomi `System.CodeDom` definisce i tipi che possono rappresentare la struttura logica del codice sorgente, in modo indipendente da un linguaggio di programmazione specifico.</span><span class="sxs-lookup"><span data-stu-id="85b19-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="85b19-106">Lo spazio dei nomi `System.CodeDom.Compiler` definisce i tipi per la generazione di codice sorgente a partire dai grafici CodeDOM e la gestione della compilazione del codice sorgente nei linguaggi supportati.</span><span class="sxs-lookup"><span data-stu-id="85b19-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="85b19-107">I produttori di compilatori o gli sviluppatori possono estendere il set di linguaggi supportati.</span><span class="sxs-lookup"><span data-stu-id="85b19-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="85b19-108">La modellazione di codice sorgente indipendente da uno specifico linguaggio si rivela particolarmente utile quando occorre che un programma generi codice sorgente per un modello di programma in più linguaggi o in un linguaggio di destinazione non ancora definito.</span><span class="sxs-lookup"><span data-stu-id="85b19-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="85b19-109">Alcuni progettisti usano ad esempio CodeDOM come interfaccia indipendente dal linguaggio per produrre codice sorgente nel linguaggio di programmazione desiderato, ove sia disponibile il supporto CodeDOM per il linguaggio.</span><span class="sxs-lookup"><span data-stu-id="85b19-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="85b19-110">.NET Framework include generatori di codice e compilatori di codice per i seguenti linguaggi: <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="85b19-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85b19-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="85b19-111">In This Section</span></span>  
 [<span data-ttu-id="85b19-112">Uso di CodeDOM</span><span class="sxs-lookup"><span data-stu-id="85b19-112">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 <span data-ttu-id="85b19-113">Vengono descritti gli usi più comuni e viene illustrata la compilazione di un semplice oggetto grafico mediante l'uso di CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="85b19-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="85b19-114">Generazione di codice sorgente e compilazione di un programma a partire da un grafico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="85b19-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="85b19-115">Viene descritto come generare codice sorgente e compilare il codice generato con un compilatore esterno usando le classi definite nello spazio dei nomi `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="85b19-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 <span data-ttu-id="85b19-116">[How to: Create an XML Documentation File Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md) (Procedura: Creare un file di documentazione XML tramite CodeDOM)</span><span class="sxs-lookup"><span data-stu-id="85b19-116">[How to: Create an XML Documentation File Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)</span></span>  
 <span data-ttu-id="85b19-117">Viene descritto come usare CodeDOM per generare codice con commenti di documentazione XML e come compilare il codice generato in modo da creare l'output della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="85b19-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="85b19-118">Procedura: Creare una classe tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="85b19-118">How to: Create a Class Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="85b19-119">Viene descritto come usare CodeDOM per generare una classe contenente campi, proprietà, un metodo, un costruttore e un punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="85b19-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="85b19-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="85b19-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="85b19-121">Definisce elementi che rappresentano elementi di codice in linguaggi di programmazione che si avvalgono del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="85b19-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="85b19-122">Definisce le interfacce per la generazione e la compilazione di codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85b19-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="85b19-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="85b19-123">Related Sections</span></span>  
 [<span data-ttu-id="85b19-124">Riferimento rapido per CodeDOM</span><span class="sxs-lookup"><span data-stu-id="85b19-124">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/library/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 <span data-ttu-id="85b19-125">Offre agli sviluppatori un modo rapido per cercare elementi CodeDOM che rappresentano elementi del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="85b19-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
