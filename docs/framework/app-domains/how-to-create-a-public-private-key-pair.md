---
title: 'Procedura: Creare una coppia di chiavi pubblica/privata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe799e15655d4ae1d9d9b7303728b503a5e45082
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741750"
---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="0d4cc-102">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="0d4cc-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="0d4cc-103">Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="0d4cc-104">Questa coppia di chiavi crittografiche, pubblica e privata, viene usata durante la compilazione per creare un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="0d4cc-105">È possibile creare una coppia di chiavi usando lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0d4cc-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="0d4cc-106">Ai file delle coppie di chiavi è in genere associata l'estensione snk.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d4cc-107">In Visual Studio le pagine delle proprietà del progetto C# e Visual Basic includono una scheda **Firma**, che consente di selezionare i file di chiave esistenti o di generarne di nuovi senza usare Sn.exe.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-107">In Visual Studio, the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="0d4cc-108">In Visual C++ è possibile specificare il percorso di un file di chiave esistente nella pagina delle proprietà **Avanzate** nella sezione **Linker** della sezione **Proprietà di configurazione** della finestra **Pagine delle proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="0d4cc-109">L'uso dell'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> per l'identificazione delle coppie di file di chiave è diventato obsoleto a partire da [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d4cc-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="0d4cc-110">Per creare una coppia di chiavi</span><span class="sxs-lookup"><span data-stu-id="0d4cc-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="0d4cc-111">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="0d4cc-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="0d4cc-112">**sn –k** \<*nome file*></span><span class="sxs-lookup"><span data-stu-id="0d4cc-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="0d4cc-113">In questo comando *nome file* corrisponde al nome del file di output contenente la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="0d4cc-114">L'esempio seguente consente di creare una coppia di chiavi denominata `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="0d4cc-115">Se si desidera ritardare la firma di un assembly e si controlla l'intera coppia di chiavi (situazione improbabile al di fuori degli scenari di testing), è possibile usare i comandi seguenti per generare una coppia di chiavi e quindi estrarre da tale coppia la chiave pubblica, che viene salvata in un file distinto.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="0d4cc-116">Creare innanzitutto la coppia di chiavi:</span><span class="sxs-lookup"><span data-stu-id="0d4cc-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="0d4cc-117">Estrarre quindi la chiave pubblica dalla coppia di chiavi e copiarla in un file distinto:</span><span class="sxs-lookup"><span data-stu-id="0d4cc-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="0d4cc-118">Dopo avere creato la coppia di chiavi, è necessario salvare il file in una posizione accessibile agli strumenti di firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="0d4cc-119">Quando firma un assembly con un nome sicuro, [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) cerca il file della chiave relativo alla directory corrente e alla directory di output.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="0d4cc-120">Se si utilizzano i compilatori della riga di comando, è sufficiente copiare la chiave nella directory corrente contenente i moduli di codice.</span><span class="sxs-lookup"><span data-stu-id="0d4cc-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="0d4cc-121">Se si usa una versione precedente di Visual Studio in cui non è disponibile una scheda **Firma** nelle proprietà del progetto, il percorso del file di chiave consigliato è la directory del progetto con l'attributo di file specificato come segue:</span><span class="sxs-lookup"><span data-stu-id="0d4cc-121">If you are using an earlier version of Visual Studio that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="0d4cc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d4cc-122">See Also</span></span>  
 [<span data-ttu-id="0d4cc-123">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="0d4cc-123">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
