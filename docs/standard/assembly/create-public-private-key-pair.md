---
title: 'Procedura: Creare una coppia di chiavi pubblica/privata'
ms.date: 08/20/2019
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
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 8a9845e3cd18ff86ec04216ad0e9c5606186b113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73122524"
---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="7fa0e-102">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="7fa0e-102">How to: Create a public-private key pair</span></span>

<span data-ttu-id="7fa0e-103">Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="7fa0e-104">Questa coppia di chiavi crittografiche, pubblica e privata, viene usata durante la compilazione per creare un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="7fa0e-105">È possibile creare una coppia di chiavi usando lo [strumento Nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7fa0e-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="7fa0e-106">I file di coppia di chiavi hanno in genere un'estensione *.snk.*</span><span class="sxs-lookup"><span data-stu-id="7fa0e-106">Key pair files usually have an *.snk* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="7fa0e-107">In Visual Studio, le pagine delle proprietà del progetto di Visual Basic e di Visual Basic includono una scheda **Firma** che consente di selezionare i file di chiave esistenti o di generare nuovi file di chiave senza *utilizzare Sn.exe*.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-107">In Visual Studio, the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using *Sn.exe*.</span></span> <span data-ttu-id="7fa0e-108">In Visual C++ è possibile specificare il percorso di un file di chiave esistente nella pagina delle proprietà **Avanzate** nella sezione **Linker** della sezione **Proprietà di configurazione** della finestra **Pagine delle proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="7fa0e-109">L'utilizzo <xref:System.Reflection.AssemblyKeyFileAttribute> dell'attributo per identificare le coppie di file di chiave è stato reso obsoleto a partire da Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs was made obsolete beginning with Visual Studio 2005.</span></span>

## <a name="create-a-key-pair"></a><span data-ttu-id="7fa0e-110">Creare una coppia di chiaviCreate a key pair</span><span class="sxs-lookup"><span data-stu-id="7fa0e-110">Create a key pair</span></span>

<span data-ttu-id="7fa0e-111">Per creare una coppia di chiavi, al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7fa0e-111">To create a key pair, at a command prompt, type the following command:</span></span>

<span data-ttu-id="7fa0e-112">**sn –k** \<*nome file*></span><span class="sxs-lookup"><span data-stu-id="7fa0e-112">**sn –k** \<*file name*></span></span>

<span data-ttu-id="7fa0e-113">In questo comando *nome file* corrisponde al nome del file di output contenente la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>

<span data-ttu-id="7fa0e-114">Nell'esempio riportato di seguito viene creata una coppia di chiavi denominata *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-114">The following example creates a key pair called *sgKey.snk*.</span></span>

```cmd
sn -k sgKey.snk
```

<span data-ttu-id="7fa0e-115">Se si desidera ritardare la firma di un assembly e si controlla l'intera coppia di chiavi (situazione improbabile al di fuori degli scenari di testing), è possibile usare i comandi seguenti per generare una coppia di chiavi e quindi estrarre da tale coppia la chiave pubblica, che viene salvata in un file distinto.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="7fa0e-116">Creare innanzitutto la coppia di chiavi:</span><span class="sxs-lookup"><span data-stu-id="7fa0e-116">First, create the key pair:</span></span>

```cmd
sn -k keypair.snk
```

<span data-ttu-id="7fa0e-117">Estrarre quindi la chiave pubblica dalla coppia di chiavi e copiarla in un file distinto:</span><span class="sxs-lookup"><span data-stu-id="7fa0e-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>

```cmd
sn -p keypair.snk public.snk
```

<span data-ttu-id="7fa0e-118">Dopo avere creato la coppia di chiavi, è necessario salvare il file in una posizione accessibile agli strumenti di firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>

<span data-ttu-id="7fa0e-119">Quando firma un assembly con un nome sicuro, [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) cerca il file della chiave relativo alla directory corrente e alla directory di output.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="7fa0e-120">Se si utilizzano i compilatori della riga di comando, è sufficiente copiare la chiave nella directory corrente contenente i moduli di codice.</span><span class="sxs-lookup"><span data-stu-id="7fa0e-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>

<span data-ttu-id="7fa0e-121">Se si usa una versione precedente di Visual Studio in cui non è disponibile una scheda **Firma** nelle proprietà del progetto, il percorso del file di chiave consigliato è la directory del progetto con l'attributo di file specificato come segue:</span><span class="sxs-lookup"><span data-stu-id="7fa0e-121">If you are using an earlier version of Visual Studio that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a><span data-ttu-id="7fa0e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fa0e-122">See also</span></span>

- [<span data-ttu-id="7fa0e-123">Creare e usare gli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="7fa0e-123">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
