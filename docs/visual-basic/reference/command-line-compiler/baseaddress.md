---
title: /baseaddress | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5687f119a57e0e54eca4df8f91fdf5e8b2775f82
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="baseaddress"></a><span data-ttu-id="cffda-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="cffda-102">/baseaddress</span></span>
<span data-ttu-id="cffda-103">Specifica un indirizzo di base predefinito durante la creazione di una DLL.</span><span class="sxs-lookup"><span data-stu-id="cffda-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cffda-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="cffda-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cffda-105">Arguments</span></span>  
  
|<span data-ttu-id="cffda-106">Termine</span><span class="sxs-lookup"><span data-stu-id="cffda-106">Term</span></span>|<span data-ttu-id="cffda-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="cffda-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="cffda-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cffda-108">Required.</span></span> <span data-ttu-id="cffda-109">L'indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="cffda-109">The base address for the DLL.</span></span> <span data-ttu-id="cffda-110">Questo indirizzo deve essere specificato come numero esadecimale.</span><span class="sxs-lookup"><span data-stu-id="cffda-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffda-111">Note</span><span class="sxs-lookup"><span data-stu-id="cffda-111">Remarks</span></span>  
 <span data-ttu-id="cffda-112">L'indirizzo di base predefinito per una DLL è impostato il [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="cffda-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
 <span data-ttu-id="cffda-113">Tenere presente che la parola di ordine inferiore in questo indirizzo viene arrotondata.</span><span class="sxs-lookup"><span data-stu-id="cffda-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="cffda-114">Ad esempio, se si specifica 0x11110001, verrà arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="cffda-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="cffda-115">Per completare il processo di firma di una DLL, utilizzare il `–R` opzione dello strumento nome sicuro (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="cffda-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="cffda-116">Questa opzione viene ignorata se la destinazione non è una DLL.</span><span class="sxs-lookup"><span data-stu-id="cffda-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="cffda-117">Per impostare /baseaddress nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cffda-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="cffda-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="cffda-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cffda-119">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cffda-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="cffda-120">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="cffda-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="cffda-121">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="cffda-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="cffda-122">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="cffda-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="cffda-123">4.  Modificare il valore di **indirizzo di base DLL:** casella.</span><span class="sxs-lookup"><span data-stu-id="cffda-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="cffda-124">**Nota:** il **indirizzo di base DLL:** casella è di sola lettura, a meno che la destinazione è una DLL.</span><span class="sxs-lookup"><span data-stu-id="cffda-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cffda-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cffda-125">See Also</span></span>  
 <span data-ttu-id="cffda-126">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="cffda-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="cffda-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="cffda-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="cffda-128"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="cffda-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="cffda-129"> [Sn.exe (strumento nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23)</span><span class="sxs-lookup"><span data-stu-id="cffda-129"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span></span>
