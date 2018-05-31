---
title: 'Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472776"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="6275d-102">Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6275d-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="6275d-103">L'esempio seguente fornisce una panoramica di base di un tipo documentato.</span><span class="sxs-lookup"><span data-stu-id="6275d-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6275d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6275d-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

<span data-ttu-id="6275d-105">L'esempio genera un file con estensione XML con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="6275d-105">The example generates an .xml file with the following contents:</span></span>

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a><span data-ttu-id="6275d-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6275d-106">Compiling the Code</span></span>  
 <span data-ttu-id="6275d-107">Per compilare l'esempio, digitare la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6275d-107">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="6275d-108">Verrà creato il file XML XMLsample.xml, che è possibile visualizzare nel browser o tramite il comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="6275d-108">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6275d-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="6275d-109">Robust Programming</span></span>  
 <span data-ttu-id="6275d-110">La documentazione XML inizia con ///.</span><span class="sxs-lookup"><span data-stu-id="6275d-110">XML documentation starts with ///.</span></span> <span data-ttu-id="6275d-111">Quando si crea un nuovo progetto, le procedure guidate inseriscono alcune linee /// iniziali.</span><span class="sxs-lookup"><span data-stu-id="6275d-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="6275d-112">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="6275d-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="6275d-113">La documentazione deve essere in codice XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="6275d-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="6275d-114">Se il codice XML non è ben formato, viene generato un avviso e il file di documentazione conterrà un commento che segnalerà che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="6275d-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="6275d-115">Gli sviluppatori sono liberi di creare set di tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6275d-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="6275d-116">Esiste un set di tag consigliato (vedere [Tag consigliati per i commenti relativi alla documentazione](recommended-tags-for-documentation-comments.md)).</span><span class="sxs-lookup"><span data-stu-id="6275d-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="6275d-117">Alcuni tag consigliati hanno un significato speciale:</span><span class="sxs-lookup"><span data-stu-id="6275d-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="6275d-118">Il tag \< viene usato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="6275d-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="6275d-119">Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="6275d-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="6275d-120">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="6275d-120">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="6275d-121">L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="6275d-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="6275d-122">Il compilatore verifica l'esistenza di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="6275d-122">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="6275d-123">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="6275d-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="6275d-124">Il compilatore rispetta eventuali istruzioni `using` quando esegue la ricerca di un tipo descritto nell'attributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="6275d-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="6275d-125">Il tag \< è usato da IntelliSense all'interno di Visual Studio per visualizzare altre informazioni su un tipo o su un membro.</span><span class="sxs-lookup"><span data-stu-id="6275d-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6275d-126">Il file XML non fornisce informazioni complete sul tipo e sui membri, ad esempio, non contiene alcuna informazione sul tipo.</span><span class="sxs-lookup"><span data-stu-id="6275d-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="6275d-127">Per ottenere informazioni complete su un tipo o su un membro, è necessario usare il file di documentazione con reflection sul tipo o sul membro effettivo.</span><span class="sxs-lookup"><span data-stu-id="6275d-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6275d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6275d-128">See Also</span></span>  
 [<span data-ttu-id="6275d-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6275d-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6275d-130">/doc (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6275d-130">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="6275d-131">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="6275d-131">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
