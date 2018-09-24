---
title: Applicazione di attributi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d28da0c788d40222ccd689807d6e51f66b4ce78
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46567818"
---
# <a name="applying-attributes"></a><span data-ttu-id="85639-102">Applicazione di attributi</span><span class="sxs-lookup"><span data-stu-id="85639-102">Applying Attributes</span></span>
<span data-ttu-id="85639-103">Usare il processo seguente per applicare un attributo a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="85639-103">Use the following process to apply an attribute to an element of your code.</span></span>  
  
1.  <span data-ttu-id="85639-104">Definire un nuovo attributo o usare un attributo esistente importando lo spazio dei nomi da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85639-104">Define a new attribute or use an existing attribute by importing its namespace from the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="85639-105">Applicare l'attributo dell'elemento di codice posizionandolo immediatamente prima dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="85639-105">Apply the attribute to the code element by placing it immediately before the element.</span></span>  
  
     <span data-ttu-id="85639-106">Ogni linguaggio ha una propria sintassi di attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-106">Each language has its own attribute syntax.</span></span> <span data-ttu-id="85639-107">In C++ e C#, l'attributo è racchiuso tra parentesi quadre e separato dall'elemento da spazi vuoti, che possono includere un'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="85639-107">In C++ and C#, the attribute is surrounded by square brackets and separated from the element by white space, which can include a line break.</span></span> <span data-ttu-id="85639-108">In Visual Basic, l'attributo è racchiuso tra parentesi acute e deve essere nella stessa riga logica. Se si desidera un'interruzione di riga, è possibile usare il carattere di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="85639-108">In Visual Basic, the attribute is surrounded by angle brackets and must be on the same logical line; the line continuation character can be used if a line break is desired.</span></span>
  
3.  <span data-ttu-id="85639-109">Specificare i parametri posizionali e i parametri denominati per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-109">Specify positional parameters and named parameters for the attribute.</span></span>  
  
     <span data-ttu-id="85639-110">I parametri posizionali sono necessari e devono precedere eventuali parametri denominati. Corrispondono ai parametri di uno dei costruttori dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-110">Positional parameters are required and must come before any named parameters; they correspond to the parameters of one of the attribute's constructors.</span></span> <span data-ttu-id="85639-111">I parametri denominati sono facoltativi e corrispondono a proprietà dell'attributo di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="85639-111">Named parameters are optional and correspond to read/write properties of the attribute.</span></span> <span data-ttu-id="85639-112">In C++ e C# specificare `name`=`value` per ciascun parametro facoltativo, in cui `name` è il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="85639-112">In C++, and C#, specify `name`=`value` for each optional parameter, where `name` is the name of the property.</span></span> <span data-ttu-id="85639-113">In Visual Basic specificare `name`:=`value`.</span><span class="sxs-lookup"><span data-stu-id="85639-113">In Visual Basic, specify `name`:=`value`.</span></span>  
  
 <span data-ttu-id="85639-114">L'attributo viene emesso nei metadati quando si compila il codice ed è disponibile per il Common Language Runtime e qualsiasi strumento personalizzato o l'applicazione tramite i servizi di reflection di runtime.</span><span class="sxs-lookup"><span data-stu-id="85639-114">The attribute is emitted into metadata when you compile your code and is available to the common language runtime and any custom tool or application through the runtime reflection services.</span></span>  
  
 <span data-ttu-id="85639-115">Per convenzione, tutti i nomi dell'attributo terminano con Attribute.</span><span class="sxs-lookup"><span data-stu-id="85639-115">By convention, all attribute names end with Attribute.</span></span> <span data-ttu-id="85639-116">Tuttavia, per molti linguaggi destinati al runtime, come Visual Basic e C#, non è necessario specificare il nome completo di un attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-116">However, several languages that target the runtime, such as Visual Basic and C#, do not require you to specify the full name of an attribute.</span></span> <span data-ttu-id="85639-117">Ad esempio, se si desidera inizializzare <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, è necessario farvi riferimento come **Obsolete**.</span><span class="sxs-lookup"><span data-stu-id="85639-117">For example, if you want to initialize <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, you only need to reference it as **Obsolete**.</span></span>  
  
## <a name="applying-an-attribute-to-a-method"></a><span data-ttu-id="85639-118">Applicazione di un attributo a un metodo</span><span class="sxs-lookup"><span data-stu-id="85639-118">Applying an Attribute to a Method</span></span>  
 <span data-ttu-id="85639-119">L'esempio di codice seguente illustra come dichiarare **System.ObsoleteAttribute**, che marca il codice come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="85639-119">The following code example shows how to declare **System.ObsoleteAttribute**, which marks code as obsolete.</span></span> <span data-ttu-id="85639-120">La stringa `"Will be removed in next version"` viene passato all'attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-120">The string `"Will be removed in next version"` is passed to the attribute.</span></span> <span data-ttu-id="85639-121">Questo attributo genera un avviso del compilatore che mostra la stringa passata quando viene chiamato il codice descritto dall'attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-121">This attribute causes a compiler warning that displays the passed string when code that the attribute describes is called.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a><span data-ttu-id="85639-122">Applicazione di attributi a livello di assembly</span><span class="sxs-lookup"><span data-stu-id="85639-122">Applying Attributes at the Assembly Level</span></span>  
 <span data-ttu-id="85639-123">Se si desidera applicare un attributo a livello di assembly usare la parola chiave **assembly** (`Assembly` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="85639-123">If you want to apply an attribute at the assembly level, use the **assembly** (`Assembly` in Visual Basic) keyword.</span></span> <span data-ttu-id="85639-124">Nel codice riportato di seguito viene illustrato l'attributo **AssemblyTitleAttribute** applicato a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="85639-124">The following code shows the **AssemblyTitleAttribute** applied at the assembly level.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 <span data-ttu-id="85639-125">Quando viene applicato questo attributo, la stringa `"My Assembly"` viene inserita nel manifesto dell'assembly nella porzione di metadati del file.</span><span class="sxs-lookup"><span data-stu-id="85639-125">When this attribute is applied, the string `"My Assembly"` is placed in the assembly manifest in the metadata portion of the file.</span></span> <span data-ttu-id="85639-126">È possibile visualizzare l'attributo tramite [Disassembler MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o creando un programma personalizzato per recuperare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="85639-126">You can view the attribute either by using the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by creating a custom program to retrieve the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85639-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85639-127">See also</span></span>

- [<span data-ttu-id="85639-128">Attributi</span><span class="sxs-lookup"><span data-stu-id="85639-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
- [<span data-ttu-id="85639-129">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="85639-129">Retrieving Information Stored in Attributes</span></span>](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)  
- [<span data-ttu-id="85639-130">Concetti</span><span class="sxs-lookup"><span data-stu-id="85639-130">Concepts</span></span>](/cpp/windows/attributed-programming-concepts)  
- [<span data-ttu-id="85639-131">Attributi</span><span class="sxs-lookup"><span data-stu-id="85639-131">Attributes</span></span>](https://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
