---
title: Generazione e compilazione dinamica di codice sorgente
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
ms.openlocfilehash: 7379bac07de9b78369d3742fa3288f6fea6a573f
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544991"
---
# <a name="compile-and-generate-dynamic-source-code"></a><span data-ttu-id="64db9-102">Compilare e generare codice sorgente dinamico</span><span class="sxs-lookup"><span data-stu-id="64db9-102">Compile and generate dynamic source code</span></span>

<span data-ttu-id="64db9-103">.NET Framework include un meccanismo denominato Code Document Object Model (CodeDOM) che consente agli sviluppatori di programmi che creano codice sorgente di generarlo, in fase di esecuzione, in più linguaggi di programmazione in base a un unico modello che rappresenta il codice da generare.</span><span class="sxs-lookup"><span data-stu-id="64db9-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
<span data-ttu-id="64db9-104">Per rappresentare il codice sorgente, gli elementi CodeDOM vengono collegati tra loro per formare una struttura di dati nota come grafico CodeDOM che modella la struttura del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="64db9-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
<span data-ttu-id="64db9-105">Lo spazio dei nomi <xref:System.CodeDom?displayProperty=fullName> definisce i tipi che possono rappresentare la struttura logica del codice sorgente, in modo indipendente da un linguaggio di programmazione specifico.</span><span class="sxs-lookup"><span data-stu-id="64db9-105">The <xref:System.CodeDom?displayProperty=fullName> namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="64db9-106">Lo spazio dei nomi <xref:System.CodeDom.Compiler?displayProperty=fullName> definisce i tipi per la generazione di codice sorgente a partire dai grafici CodeDOM e la gestione della compilazione del codice sorgente nei linguaggi supportati.</span><span class="sxs-lookup"><span data-stu-id="64db9-106">The <xref:System.CodeDom.Compiler?displayProperty=fullName> namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="64db9-107">I produttori di compilatori o gli sviluppatori possono estendere il set di linguaggi supportati.</span><span class="sxs-lookup"><span data-stu-id="64db9-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
<span data-ttu-id="64db9-108">La modellazione di codice sorgente indipendente da uno specifico linguaggio si rivela particolarmente utile quando occorre che un programma generi codice sorgente per un modello di programma in più linguaggi o in un linguaggio di destinazione non ancora definito.</span><span class="sxs-lookup"><span data-stu-id="64db9-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="64db9-109">Alcuni progettisti usano ad esempio CodeDOM come interfaccia indipendente dal linguaggio per produrre codice sorgente nel linguaggio di programmazione desiderato, ove sia disponibile il supporto CodeDOM per il linguaggio.</span><span class="sxs-lookup"><span data-stu-id="64db9-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
<span data-ttu-id="64db9-110">.NET Framework include generatori di codice e compilatori di codice per i seguenti linguaggi: <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="64db9-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64db9-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="64db9-111">In this section</span></span>

- [<span data-ttu-id="64db9-112">Uso di CodeDOM</span><span class="sxs-lookup"><span data-stu-id="64db9-112">Using the CodeDOM</span></span>](using-the-codedom.md)

  <span data-ttu-id="64db9-113">Vengono descritti gli usi più comuni e viene illustrata la compilazione di un semplice oggetto grafico mediante l'uso di CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="64db9-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
- [<span data-ttu-id="64db9-114">Generare codice sorgente e compilare un programma da un grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="64db9-114">Generate Source Code and Compile a Program from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  <span data-ttu-id="64db9-115">Viene descritto come generare codice sorgente e compilare il codice generato con un compilatore esterno usando le classi definite nello spazio dei nomi `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="64db9-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
- [<span data-ttu-id="64db9-116">Procedura: creare un file di documentazione XML tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="64db9-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](how-to-create-an-xml-documentation-file-using-codedom.md)  

  <span data-ttu-id="64db9-117">Viene descritto come usare CodeDOM per generare codice con commenti di documentazione XML e come compilare il codice generato in modo da creare l'output della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="64db9-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
- [<span data-ttu-id="64db9-118">Procedura: Creare una classe tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="64db9-118">How to: Create a Class Using CodeDOM</span></span>](how-to-create-a-class-using-codedom.md)  

  <span data-ttu-id="64db9-119">Viene descritto come usare CodeDOM per generare una classe contenente campi, proprietà, un metodo, un costruttore e un punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="64db9-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="64db9-120">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="64db9-120">Reference</span></span>  

- <xref:System.CodeDom>  

  <span data-ttu-id="64db9-121">Definisce elementi che rappresentano elementi di codice in linguaggi di programmazione che si avvalgono del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="64db9-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
- <xref:System.CodeDom.Compiler>  

  <span data-ttu-id="64db9-122">Definisce le interfacce per la generazione e la compilazione di codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64db9-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="64db9-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="64db9-123">Related sections</span></span>  

- <span data-ttu-id="64db9-124">Il [riferimento rapido per CodeDom](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) fornisce agli sviluppatori un modo rapido per trovare gli elementi CodeDOM che rappresentano gli elementi del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="64db9-124">[CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
