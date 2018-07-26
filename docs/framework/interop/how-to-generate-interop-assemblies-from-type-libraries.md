---
title: 'Procedura: generare assembly di interoperabilità da librerie dei tipi'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62d9213e58aaabd0b4001d5c6a7fd6fd375eba2e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874858"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="17f81-102">Procedura: generare assembly di interoperabilità da librerie dei tipi</span><span class="sxs-lookup"><span data-stu-id="17f81-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="17f81-103">[Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) è uno strumento da riga di comando che converte in metadati le coclassi e le interfacce contenute in una libreria dei tipi COM.</span><span class="sxs-lookup"><span data-stu-id="17f81-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="17f81-104">Questo strumento crea automaticamente un assembly di interoperabilità e lo spazio dei nomi per le informazioni sui tipi.</span><span class="sxs-lookup"><span data-stu-id="17f81-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="17f81-105">Dopo che i metadati di una classe sono disponibili, i client gestiti possono creare istanze del tipo COM e chiamarne i metodi, come se si trattasse di un'istanza di .NET.</span><span class="sxs-lookup"><span data-stu-id="17f81-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="17f81-106">Tlbimp.exe converte un'intera libreria dei tipi in metadati in una sola operazione e non può generare informazioni sui tipi per un subset dei tipi definiti in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="17f81-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="17f81-107">Per generare un assembly di interoperabilità da una libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="17f81-107">To generate an interop assembly from a type library</span></span>  
  
1.  <span data-ttu-id="17f81-108">Utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="17f81-108">Use the following command:</span></span>  
  
     <span data-ttu-id="17f81-109">**tlbimp** \<*file-libreria-tipi*></span><span class="sxs-lookup"><span data-stu-id="17f81-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="17f81-110">L'aggiunta dell'opzione **/out:** produce un assembly di interoperabilità con un nome modificato, ad esempio LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="17f81-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="17f81-111">La modifica del nome di assembly di interoperabilità può essere utile per distinguerlo dalla DLL COM originale e impedire che si verifichino problemi a causa di nomi duplicati.</span><span class="sxs-lookup"><span data-stu-id="17f81-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17f81-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="17f81-112">Example</span></span>  
 <span data-ttu-id="17f81-113">Il comando seguente produce l'assembly Loanlib.dll nello spazio dei nomi `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="17f81-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="17f81-114">Il comando seguente produce un assembly di interoperabilità con un nome modificato (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="17f81-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="17f81-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17f81-115">See Also</span></span>  
 [<span data-ttu-id="17f81-116">Importazione di una libreria dei tipi come assembly</span><span class="sxs-lookup"><span data-stu-id="17f81-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="17f81-117">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17f81-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)
