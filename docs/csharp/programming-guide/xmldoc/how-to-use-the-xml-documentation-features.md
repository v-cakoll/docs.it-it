---
title: 'Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 6c7e30d23868959145e8941057f1c633fe6e374e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="12dea-102">Procedura: utilizzare le funzionalità relative alla documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="12dea-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="12dea-103">L'esempio seguente fornisce una panoramica di base di un tipo documentato.</span><span class="sxs-lookup"><span data-stu-id="12dea-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12dea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="12dea-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="12dea-105">**// Questo file con estensione xml è stato generato con il codice di esempio precedente.**</span><span class="sxs-lookup"><span data-stu-id="12dea-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="12dea-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="12dea-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="12dea-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="12dea-107">**\<doc>**</span></span>  
 <span data-ttu-id="12dea-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="12dea-108">**\<assembly>**</span></span>  
 <span data-ttu-id="12dea-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="12dea-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="12dea-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="12dea-110">**\</assembly>**</span></span>  
 <span data-ttu-id="12dea-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="12dea-111">**\<members>**</span></span>  
 <span data-ttu-id="12dea-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="12dea-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="12dea-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-113">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-114">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="12dea-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="12dea-115">**\<remarks>**</span></span>  
 <span data-ttu-id="12dea-116">**È possibile associare commenti più estesi a un tipo o un membro**</span><span class="sxs-lookup"><span data-stu-id="12dea-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="12dea-117">**through the remarks tag\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="12dea-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="12dea-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-118">**\</member>**</span></span>  
 <span data-ttu-id="12dea-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="12dea-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="12dea-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-120">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-121">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="12dea-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-122">**\</member>**</span></span>  
 <span data-ttu-id="12dea-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="12dea-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="12dea-124">**\<summary>The class constructor.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="12dea-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-125">**\</member>**</span></span>  
 <span data-ttu-id="12dea-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="12dea-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="12dea-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-127">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-128">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="12dea-129">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="12dea-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="12dea-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="12dea-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="12dea-131">**È possibile utilizzare l'attributo cref in qualsiasi tag per fare riferimento a un tipo o a un membro**</span><span class="sxs-lookup"><span data-stu-id="12dea-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="12dea-132">**and the compiler will check that the reference exists. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="12dea-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="12dea-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-133">**\</member>**</span></span>  
 <span data-ttu-id="12dea-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="12dea-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="12dea-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-135">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-136">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="12dea-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="12dea-137">**\<returns>**</span></span>  
 <span data-ttu-id="12dea-138">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="12dea-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="12dea-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="12dea-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="12dea-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="12dea-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="12dea-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-141">**\</member>**</span></span>  
 <span data-ttu-id="12dea-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="12dea-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="12dea-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-143">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-144">**Punto di ingresso dell'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="12dea-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="12dea-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-145">**\</summary>**</span></span>  
 <span data-ttu-id="12dea-146">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="12dea-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="12dea-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-147">**\</member>**</span></span>  
 <span data-ttu-id="12dea-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="12dea-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="12dea-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-149">**\<summary>**</span></span>  
 <span data-ttu-id="12dea-150">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="12dea-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="12dea-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="12dea-151">**\<value>**</span></span>  
 <span data-ttu-id="12dea-152">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="12dea-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="12dea-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="12dea-153">**\</member>**</span></span>  
 <span data-ttu-id="12dea-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="12dea-154">**\</members>**</span></span>  
<span data-ttu-id="12dea-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="12dea-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="12dea-156">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="12dea-156">Compiling the Code</span></span>  
 <span data-ttu-id="12dea-157">Per compilare l'esempio, digitare la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="12dea-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="12dea-158">Verrà creato il file XML XMLsample.xml, che è possibile visualizzare nel browser o tramite il comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="12dea-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="12dea-159">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="12dea-159">Robust Programming</span></span>  
 <span data-ttu-id="12dea-160">La documentazione XML inizia con ///.</span><span class="sxs-lookup"><span data-stu-id="12dea-160">XML documentation starts with ///.</span></span> <span data-ttu-id="12dea-161">Quando si crea un nuovo progetto, le procedure guidate inseriscono alcune linee /// iniziali.</span><span class="sxs-lookup"><span data-stu-id="12dea-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="12dea-162">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="12dea-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="12dea-163">La documentazione deve essere in codice XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="12dea-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="12dea-164">Se il codice XML non è ben formato, viene generato un avviso e il file di documentazione conterrà un commento che segnalerà che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="12dea-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="12dea-165">Gli sviluppatori sono liberi di creare set di tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="12dea-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="12dea-166">È disponibile un set di tag consigliato (vedere la sezione Altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="12dea-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="12dea-167">Alcuni tag consigliati hanno un significato speciale:</span><span class="sxs-lookup"><span data-stu-id="12dea-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="12dea-168">Il tag \< viene usato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="12dea-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="12dea-169">Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="12dea-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="12dea-170">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="12dea-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="12dea-171">L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="12dea-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="12dea-172">Il compilatore verifica l'esistenza di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="12dea-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="12dea-173">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="12dea-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="12dea-174">Il compilatore rispetta eventuali istruzioni `using` quando esegue la ricerca di un tipo descritto nell'attributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="12dea-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="12dea-175">Il tag \< è usato da IntelliSense all'interno di Visual Studio per visualizzare altre informazioni su un tipo o su un membro.</span><span class="sxs-lookup"><span data-stu-id="12dea-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="12dea-176">Il file XML non fornisce informazioni complete sul tipo e sui membri, ad esempio, non contiene alcuna informazione sul tipo.</span><span class="sxs-lookup"><span data-stu-id="12dea-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="12dea-177">Per ottenere informazioni complete su un tipo o su un membro, è necessario usare il file di documentazione con reflection sul tipo o sul membro effettivo.</span><span class="sxs-lookup"><span data-stu-id="12dea-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12dea-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12dea-178">See Also</span></span>  
 [<span data-ttu-id="12dea-179">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="12dea-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="12dea-180">/doc (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="12dea-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="12dea-181">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="12dea-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
