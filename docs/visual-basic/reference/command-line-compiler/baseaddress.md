---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 0550e4ad700494c8773a5d9b5b282dfa116adfed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813366"
---
# <a name="-baseaddress"></a><span data-ttu-id="a77ad-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="a77ad-102">-baseaddress</span></span>
<span data-ttu-id="a77ad-103">Specifica un indirizzo di base predefinito durante la creazione di una DLL.</span><span class="sxs-lookup"><span data-stu-id="a77ad-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a77ad-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="a77ad-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a77ad-105">Arguments</span></span>  
  
|<span data-ttu-id="a77ad-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a77ad-106">Term</span></span>|<span data-ttu-id="a77ad-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a77ad-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="a77ad-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a77ad-108">Required.</span></span> <span data-ttu-id="a77ad-109">Indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="a77ad-109">The base address for the DLL.</span></span> <span data-ttu-id="a77ad-110">Questo indirizzo deve essere specificato come numero esadecimale.</span><span class="sxs-lookup"><span data-stu-id="a77ad-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a77ad-111">Note</span><span class="sxs-lookup"><span data-stu-id="a77ad-111">Remarks</span></span>  
 <span data-ttu-id="a77ad-112">L'indirizzo di base predefinito per una DLL è impostata il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a77ad-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="a77ad-113">Tenere presente che la parola di ordine inferiore di questo indirizzo viene arrotondata.</span><span class="sxs-lookup"><span data-stu-id="a77ad-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="a77ad-114">Ad esempio, se si specifica 0x11110001, il valore viene arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="a77ad-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="a77ad-115">Per completare il processo di firma per una DLL, usare il `–R` opzione dello strumento nome sicuro (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="a77ad-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="a77ad-116">Questa opzione viene ignorata se la destinazione non è una DLL.</span><span class="sxs-lookup"><span data-stu-id="a77ad-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="a77ad-117">Per impostare - baseaddress nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a77ad-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="a77ad-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a77ad-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a77ad-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a77ad-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a77ad-120">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a77ad-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a77ad-121">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a77ad-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="a77ad-122">4.  Modificare il valore di **indirizzo di base DLL:** casella.</span><span class="sxs-lookup"><span data-stu-id="a77ad-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="a77ad-123">**Nota:**      Il **indirizzo di base DLL:** casella è di sola lettura, a meno che la destinazione è una DLL.</span><span class="sxs-lookup"><span data-stu-id="a77ad-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a77ad-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a77ad-124">See also</span></span>

- [<span data-ttu-id="a77ad-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a77ad-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a77ad-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a77ad-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="a77ad-127">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="a77ad-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="a77ad-128">[Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="a77ad-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
