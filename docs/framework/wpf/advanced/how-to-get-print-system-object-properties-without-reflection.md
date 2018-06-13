---
title: 'Procedura: ottenere le proprietà di un oggetto di sistema di stampa senza ricorrere alla reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: 1fa8029b8245aef5e10e9082a1038fd89fc1c84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544731"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="2d2fb-102">Procedura: ottenere le proprietà di un oggetto di sistema di stampa senza ricorrere alla reflection</span><span class="sxs-lookup"><span data-stu-id="2d2fb-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="2d2fb-103">Uso della reflection per descrivere le proprietà (e i tipi di tali proprietà) su un oggetto può rallentare le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="2d2fb-104">Il <xref:System.Printing.IndexedProperties> dello spazio dei nomi fornisce un modo per ottenere queste informazioni utilizzando la reflection.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d2fb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d2fb-105">Example</span></span>  
 <span data-ttu-id="2d2fb-106">Come indicato di seguito sono riportati i passaggi di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="2d2fb-107">Creare un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-107">Create an instance of the type.</span></span> <span data-ttu-id="2d2fb-108">Nell'esempio seguente, il tipo è il <xref:System.Printing.PrintQueue> tipo fornito con Microsoft .NET Framework, ma codice quasi identico dovrebbe funzionare per i tipi che derivano da <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="2d2fb-109">Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dalla proprietà del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="2d2fb-110">Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ciascuna voce del dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="2d2fb-111">Consente di enumerare i membri del dizionario.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="2d2fb-112">Per ognuno di essi, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="2d2fb-113">Il valore di ogni voce in upcast <xref:System.Printing.IndexedProperties.PrintProperty> e utilizzarlo per creare un <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="2d2fb-114">Ottenere il tipo di <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> di ogni il <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.</span><span class="sxs-lookup"><span data-stu-id="2d2fb-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="2d2fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d2fb-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="2d2fb-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="2d2fb-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="2d2fb-117">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="2d2fb-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
