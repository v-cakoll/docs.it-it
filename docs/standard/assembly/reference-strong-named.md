---
title: 'Procedura: fare riferimento a un assembly con nome sicuro'
description: In questo articolo viene illustrato come fare riferimento a tipi o risorse in un assembly .NET con nome sicuro in fase di compilazione o di Runtime.
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
ms.openlocfilehash: e42c1b461da16d7000605b9b9321138bbfebd307
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379870"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="3fdfd-103">Procedura: fare riferimento a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="3fdfd-103">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="3fdfd-104">Il processo per la creazione di riferimenti a tipi o risorse in un assembly con nome sicuro è solitamente trasparente all'utente.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-104">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="3fdfd-105">È possibile creare i riferimenti in fase di compilazione (associazione anticipata) o in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-105">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="3fdfd-106">Un riferimento in fase di compilazione si verifica quando si indica al compilatore che l'assembly da compilare fa riferimento in modo esplicito a un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-106">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="3fdfd-107">Quando si usano i riferimenti in fase di compilazione, il compilatore riceve automaticamente la chiave pubblica dell'assembly con nome sicuro di destinazione e inserisce la chiave nel riferimento dell'assembly in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-107">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fdfd-108">Gli assembly con nome sicuro possono usare solo tipi da altri assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-108">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="3fdfd-109">In caso contrario, la sicurezza dell'assembly con nome sicuro risulterebbe compromessa.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-109">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="3fdfd-110">Creare un riferimento in fase di compilazione a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="3fdfd-110">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="3fdfd-111">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdfd-111">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="3fdfd-112">\<*comando* >  del compilatore **/Reference:** \< *nome assembly*></span><span class="sxs-lookup"><span data-stu-id="3fdfd-112">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="3fdfd-113">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato e *nome assembly* è il nome dell'assembly con nome sicuro a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-113">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="3fdfd-114">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/t:library** per la creazione di un assembly di librerie.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-114">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="3fdfd-115">Nell'esempio seguente viene creato un assembly denominato MyAssembly *. dll* che fa riferimento a un assembly con nome sicuro denominato *myLibAssembly. dll* da un modulo di codice denominato *myAssembly.cs*.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-115">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="3fdfd-116">Creare un riferimento in fase di esecuzione a un assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="3fdfd-116">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="3fdfd-117">Quando si crea un riferimento in fase di esecuzione a un assembly con nome sicuro, ad esempio usando il <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> metodo o, è necessario usare il nome visualizzato dell'assembly con nome sicuro a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-117">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="3fdfd-118">La sintassi di un nome visualizzato è la seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdfd-118">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="3fdfd-119">\<*nome assembly* > **,** \< *numero* > di versione **,** \< *impostazioni cultura* > **,** \< *token di chiave pubblica*></span><span class="sxs-lookup"><span data-stu-id="3fdfd-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="3fdfd-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdfd-120">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="3fdfd-121">In questo esempio `PublicKeyToken` è il token di chiave pubblica in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-121">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="3fdfd-122">Se non è presente alcun valore relativo alle impostazioni cultura, usare `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-122">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="3fdfd-123">L'esempio di codice seguente illustra come usare queste informazioni con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3fdfd-123">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

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

<span data-ttu-id="3fdfd-124">È possibile stampare il formato esadecimale della chiave pubblica e del token di chiave pubblica per un assembly specifico usando il comando [Nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdfd-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="3fdfd-125">**SN-TP \< \*\* *assembly* di**>\*\*</span><span class="sxs-lookup"><span data-stu-id="3fdfd-125">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="3fdfd-126">Se è presente un file di chiave pubblica, è possibile usare il comando seguente (si noti la differenza tra maiuscole e minuscole nell'opzione della riga di comando):</span><span class="sxs-lookup"><span data-stu-id="3fdfd-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="3fdfd-127">**sn -tp \<** *file di chiave pubblica* **>**</span><span class="sxs-lookup"><span data-stu-id="3fdfd-127">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="3fdfd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fdfd-128">See also</span></span>

- [<span data-ttu-id="3fdfd-129">Creare e usare gli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="3fdfd-129">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
