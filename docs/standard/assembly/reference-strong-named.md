---
title: 'Procedura: fare riferimento a un assembly con nome sicuroHow to: Reference a strong-named assembly'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: adda4ed2ab5c59e3518b8e724044529a79840ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156478"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="79abe-102">Procedura: fare riferimento a un assembly con nome sicuroHow to: Reference a strong-named assembly</span><span class="sxs-lookup"><span data-stu-id="79abe-102">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="79abe-103">Il processo per la creazione di riferimenti a tipi o risorse in un assembly con nome sicuro è solitamente trasparente all'utente.</span><span class="sxs-lookup"><span data-stu-id="79abe-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="79abe-104">È possibile creare i riferimenti in fase di compilazione (associazione anticipata) o in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79abe-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="79abe-105">Un riferimento in fase di compilazione si verifica quando si indica al compilatore che l'assembly da compilare fa riferimento in modo esplicito a un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="79abe-105">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="79abe-106">Quando si usano i riferimenti in fase di compilazione, il compilatore riceve automaticamente la chiave pubblica dell'assembly con nome sicuro di destinazione e inserisce la chiave nel riferimento dell'assembly in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="79abe-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79abe-107">Gli assembly con nome sicuro possono usare solo tipi da altri assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="79abe-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="79abe-108">In caso contrario, la sicurezza dell'assembly con nome sicuro risulterebbe compromessa.</span><span class="sxs-lookup"><span data-stu-id="79abe-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="79abe-109">Creare un riferimento in fase di compilazione a un assembly con nome sicuroMake a compile-time reference to a strong-named assembly</span><span class="sxs-lookup"><span data-stu-id="79abe-109">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="79abe-110">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="79abe-110">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="79abe-111">\<*comando*> del compilatore **/reference:**\<*nome dell'assembly*></span><span class="sxs-lookup"><span data-stu-id="79abe-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="79abe-112">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato e *nome assembly* è il nome dell'assembly con nome sicuro a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="79abe-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="79abe-113">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/t:library** per la creazione di un assembly di librerie.</span><span class="sxs-lookup"><span data-stu-id="79abe-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="79abe-114">Nell'esempio riportato di seguito viene creato un assembly denominato *myAssembly.dll* che fa riferimento a un assembly con nome sicuro denominato *myLibAssembly.dll* da un modulo di codice denominato *myAssembly.cs*.</span><span class="sxs-lookup"><span data-stu-id="79abe-114">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="79abe-115">Creare un riferimento in fase di esecuzione a un assembly con nome sicuroMake a run-time reference to a strong-named assembly</span><span class="sxs-lookup"><span data-stu-id="79abe-115">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="79abe-116">Quando si crea un riferimento in fase di esecuzione a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> un <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> assembly con nome sicuro, ad esempio utilizzando il metodo o , è necessario utilizzare il nome visualizzato dell'assembly con nome sicuro a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="79abe-116">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="79abe-117">La sintassi di un nome visualizzato è la seguente:</span><span class="sxs-lookup"><span data-stu-id="79abe-117">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="79abe-118">\<*nome*>dell'assembly **,** \< *numero*>di versione **,** \< *impostazioni cultura*>**,** \< *token di chiave pubblica*></span><span class="sxs-lookup"><span data-stu-id="79abe-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="79abe-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79abe-119">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="79abe-120">In questo esempio `PublicKeyToken` è il token di chiave pubblica in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="79abe-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="79abe-121">Se non è presente alcun valore relativo alle impostazioni cultura, usare `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="79abe-121">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="79abe-122">L'esempio di codice seguente illustra come usare queste informazioni con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79abe-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="79abe-123">È possibile stampare il formato esadecimale della chiave pubblica e del token di chiave pubblica per un assembly specifico usando il comando [Nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="79abe-123">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="79abe-124">**Sn \< -Tp** *assemblaggio\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="79abe-124">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="79abe-125">Se è presente un file di chiave pubblica, è possibile usare il comando seguente (si noti la differenza tra maiuscole e minuscole nell'opzione della riga di comando):</span><span class="sxs-lookup"><span data-stu-id="79abe-125">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="79abe-126">**sn -tp \<** *file di chiave pubblica* **>**</span><span class="sxs-lookup"><span data-stu-id="79abe-126">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="79abe-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79abe-127">See also</span></span>

- [<span data-ttu-id="79abe-128">Creare e usare gli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="79abe-128">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
