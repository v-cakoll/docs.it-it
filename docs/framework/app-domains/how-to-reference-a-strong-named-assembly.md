---
title: 'Procedura: aggiungere un riferimento a un assembly con nome sicuro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aa46bfdfe42dca9509e39d4b6218473aa00a1877
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="f51d3-102">Procedura: aggiungere un riferimento a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="f51d3-102">How to: Reference a Strong-Named Assembly</span></span>
<span data-ttu-id="f51d3-103">Il processo per la creazione di riferimenti a tipi o risorse in un assembly con nome sicuro è solitamente trasparente all'utente.</span><span class="sxs-lookup"><span data-stu-id="f51d3-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="f51d3-104">È possibile creare i riferimenti in fase di compilazione (associazione anticipata) o in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f51d3-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
 <span data-ttu-id="f51d3-105">Un riferimento in fase di compilazione viene creato quando si indica al compilatore che l'assembly contiene riferimenti espliciti a un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="f51d3-105">A compile-time reference occurs when you indicate to the compiler that your assembly explicitly references another assembly.</span></span> <span data-ttu-id="f51d3-106">Quando si usano i riferimenti in fase di compilazione, il compilatore riceve automaticamente la chiave pubblica dell'assembly con nome sicuro di destinazione e inserisce la chiave nel riferimento dell'assembly in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f51d3-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f51d3-107">Gli assembly con nome sicuro possono usare solo tipi da altri assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="f51d3-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="f51d3-108">In caso contrario, la sicurezza dell'assembly con nome sicuro risulterebbe compromessa.</span><span class="sxs-lookup"><span data-stu-id="f51d3-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="f51d3-109">Per creare un riferimento in fase di compilazione a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="f51d3-109">To make a compile-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="f51d3-110">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="f51d3-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="f51d3-111">\<*comando compilatore*> **/reference:**\<*nome assembly*></span><span class="sxs-lookup"><span data-stu-id="f51d3-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  
  
     <span data-ttu-id="f51d3-112">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato e *nome assembly* è il nome dell'assembly con nome sicuro a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="f51d3-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="f51d3-113">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/t:library** per la creazione di un assembly di librerie.</span><span class="sxs-lookup"><span data-stu-id="f51d3-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  
  
 <span data-ttu-id="f51d3-114">L'esempio seguente crea un assembly denominato `myAssembly.dll` che fa riferimento a un assembly con nome sicuro denominato `myLibAssembly.dll` da un modulo di codice denominato `myAssembly.cs`.</span><span class="sxs-lookup"><span data-stu-id="f51d3-114">The following example creates an assembly called `myAssembly.dll` that references a strong-named assembly called `myLibAssembly.dll` from a code module called `myAssembly.cs`.</span></span>  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="f51d3-115">Per creare un riferimento in fase di esecuzione a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="f51d3-115">To make a run-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="f51d3-116">Quando si crea un riferimento in fase di esecuzione a un assembly con nome sicuro, ad esempio usando il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>, è necessario usare il nome visualizzato dell'assembly con nome sicuro a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="f51d3-116">When you make a run-time reference to a strong-named assembly (for example, by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> method), you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="f51d3-117">La sintassi di un nome visualizzato è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f51d3-117">The syntax of a display name is as follows:</span></span>  
  
     <span data-ttu-id="f51d3-118">\<*nome assembly*>**,** \<*numero versione*>**,** \<*cultura*>**,** \<*token chiave pubblica*></span><span class="sxs-lookup"><span data-stu-id="f51d3-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  
  
     <span data-ttu-id="f51d3-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f51d3-119">For example:</span></span>  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     <span data-ttu-id="f51d3-120">In questo esempio `PublicKeyToken` è il token di chiave pubblica in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="f51d3-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="f51d3-121">Se non è presente alcun valore relativo alle impostazioni cultura, usare `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="f51d3-121">If there is no culture value, use `Culture=neutral`.</span></span>  
  
 <span data-ttu-id="f51d3-122">L'esempio di codice seguente illustra come usare queste informazioni con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f51d3-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="f51d3-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="f51d3-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span></span>  
  
 <span data-ttu-id="f51d3-124">È possibile stampare il formato esadecimale della chiave pubblica e del token di chiave pubblica per un assembly specifico usando il comando [Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="f51d3-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  
  
 <span data-ttu-id="f51d3-125">**sn -Tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="f51d3-125">**sn -Tp \<** *assembly* **>**</span></span>  
  
 <span data-ttu-id="f51d3-126">Se è presente un file di chiave pubblica, è possibile usare il comando seguente (si noti la differenza tra maiuscole e minuscole nell'opzione della riga di comando):</span><span class="sxs-lookup"><span data-stu-id="f51d3-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  
  
 <span data-ttu-id="f51d3-127">**sn -tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="f51d3-127">**sn -tp \<** *assembly* **>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51d3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f51d3-128">See Also</span></span>  
 [<span data-ttu-id="f51d3-129">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="f51d3-129">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

