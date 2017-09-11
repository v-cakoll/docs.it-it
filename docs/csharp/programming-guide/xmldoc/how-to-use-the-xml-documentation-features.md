---
title: "Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="848d5-102">Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="848d5-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="848d5-103">L'esempio seguente fornisce una panoramica di base di un tipo documentato.</span><span class="sxs-lookup"><span data-stu-id="848d5-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="848d5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="848d5-104">Example</span></span>  
 <span data-ttu-id="848d5-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="848d5-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="848d5-106">**// Questo file con estensione xml è stato generato con il codice di esempio precedente.**</span><span class="sxs-lookup"><span data-stu-id="848d5-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="848d5-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="848d5-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="848d5-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="848d5-108">**\<doc>**</span></span>  
 <span data-ttu-id="848d5-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="848d5-109">**\<assembly>**</span></span>  
 <span data-ttu-id="848d5-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="848d5-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="848d5-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="848d5-111">**\</assembly>**</span></span>  
 <span data-ttu-id="848d5-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="848d5-112">**\<members>**</span></span>  
 <span data-ttu-id="848d5-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="848d5-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="848d5-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-114">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-115">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="848d5-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="848d5-116">**\<remarks>**</span></span>  
 <span data-ttu-id="848d5-117">**È possibile associare commenti più estesi a un tipo o un membro** </span><span class="sxs-lookup"><span data-stu-id="848d5-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="848d5-118">**tramite il tag remarks\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="848d5-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="848d5-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-119">**\</member>**</span></span>  
 <span data-ttu-id="848d5-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="848d5-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="848d5-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-121">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-122">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="848d5-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-123">**\</member>**</span></span>  
 <span data-ttu-id="848d5-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="848d5-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="848d5-125">**\<summary>The class constructor.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="848d5-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="848d5-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-126">**\</member>**</span></span>  
 <span data-ttu-id="848d5-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="848d5-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="848d5-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-128">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-129">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="848d5-130">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="848d5-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="848d5-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="848d5-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="848d5-132">**È possibile utilizzare l'attributo cref in qualsiasi tag per fare riferimento a un tipo o un membro.** </span><span class="sxs-lookup"><span data-stu-id="848d5-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="848d5-133">**Il compilatore verificherà l'esistenza del riferimento. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="848d5-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="848d5-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-134">**\</member>**</span></span>  
 <span data-ttu-id="848d5-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="848d5-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="848d5-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-136">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-137">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="848d5-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="848d5-138">**\<returns>**</span></span>  
 <span data-ttu-id="848d5-139">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="848d5-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="848d5-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="848d5-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="848d5-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="848d5-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="848d5-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-142">**\</member>**</span></span>  
 <span data-ttu-id="848d5-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="848d5-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="848d5-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-144">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-145">**Punto di ingresso dell'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="848d5-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="848d5-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-146">**\</summary>**</span></span>  
 <span data-ttu-id="848d5-147">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="848d5-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="848d5-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-148">**\</member>**</span></span>  
 <span data-ttu-id="848d5-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="848d5-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="848d5-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-150">**\<summary>**</span></span>  
 <span data-ttu-id="848d5-151">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="848d5-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="848d5-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="848d5-152">**\<value>**</span></span>  
 <span data-ttu-id="848d5-153">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="848d5-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="848d5-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="848d5-154">**\</member>**</span></span>  
 <span data-ttu-id="848d5-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="848d5-155">**\</members>**</span></span>  
<span data-ttu-id="848d5-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="848d5-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="848d5-157">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="848d5-157">Compiling the Code</span></span>  
 <span data-ttu-id="848d5-158">Per compilare l'esempio, digitare la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="848d5-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="848d5-159">Verrà creato il file XML XMLsample.xml, che è possibile visualizzare nel browser o tramite il comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="848d5-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="848d5-160">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="848d5-160">Robust Programming</span></span>  
 <span data-ttu-id="848d5-161">La documentazione XML inizia con ///.</span><span class="sxs-lookup"><span data-stu-id="848d5-161">XML documentation starts with ///.</span></span> <span data-ttu-id="848d5-162">Quando si crea un nuovo progetto, le procedure guidate inseriscono alcune linee /// iniziali.</span><span class="sxs-lookup"><span data-stu-id="848d5-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="848d5-163">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="848d5-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="848d5-164">La documentazione deve essere in codice XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="848d5-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="848d5-165">Se il codice XML non è ben formato, viene generato un avviso e il file di documentazione conterrà un commento che segnalerà che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="848d5-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="848d5-166">Gli sviluppatori sono liberi di creare set di tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="848d5-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="848d5-167">È disponibile un set di tag consigliato (vedere la sezione Altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="848d5-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="848d5-168">Alcuni tag consigliati hanno un significato speciale:</span><span class="sxs-lookup"><span data-stu-id="848d5-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="848d5-169">Il tag \< viene usato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="848d5-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="848d5-170">Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="848d5-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="848d5-171">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="848d5-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="848d5-172">L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="848d5-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="848d5-173">Il compilatore verifica l'esistenza di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="848d5-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="848d5-174">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="848d5-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="848d5-175">Il compilatore rispetta eventuali istruzioni `using` quando esegue la ricerca di un tipo descritto nell'attributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="848d5-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="848d5-176">Il tag \< è usato da IntelliSense all'interno di Visual Studio per visualizzare altre informazioni su un tipo o su un membro.</span><span class="sxs-lookup"><span data-stu-id="848d5-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="848d5-177">Il file XML non fornisce informazioni complete sul tipo e sui membri, ad esempio, non contiene alcuna informazione sul tipo.</span><span class="sxs-lookup"><span data-stu-id="848d5-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="848d5-178">Per ottenere informazioni complete su un tipo o su un membro, è necessario usare il file di documentazione con reflection sul tipo o sul membro effettivo.</span><span class="sxs-lookup"><span data-stu-id="848d5-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848d5-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="848d5-179">See Also</span></span>  
 <span data-ttu-id="848d5-180">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="848d5-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="848d5-181">[/doc (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="848d5-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="848d5-182">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="848d5-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

