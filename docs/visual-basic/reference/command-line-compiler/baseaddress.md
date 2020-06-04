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
ms.openlocfilehash: d241584195da7d6f74b45b191c4f63204c200d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357180"
---
# <a name="-baseaddress"></a><span data-ttu-id="2b57b-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="2b57b-102">-baseaddress</span></span>
<span data-ttu-id="2b57b-103">Specifica un indirizzo di base predefinito durante la creazione di una DLL.</span><span class="sxs-lookup"><span data-stu-id="2b57b-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b57b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b57b-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b57b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2b57b-105">Arguments</span></span>  
  
|<span data-ttu-id="2b57b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="2b57b-106">Term</span></span>|<span data-ttu-id="2b57b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="2b57b-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="2b57b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2b57b-108">Required.</span></span> <span data-ttu-id="2b57b-109">Indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="2b57b-109">The base address for the DLL.</span></span> <span data-ttu-id="2b57b-110">Questo indirizzo deve essere specificato come numero esadecimale.</span><span class="sxs-lookup"><span data-stu-id="2b57b-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b57b-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b57b-111">Remarks</span></span>  
 <span data-ttu-id="2b57b-112">L'indirizzo di base predefinito per una DLL viene impostato dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b57b-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="2b57b-113">Tenere presente che la parola di ordine inferiore in questo indirizzo viene arrotondata.</span><span class="sxs-lookup"><span data-stu-id="2b57b-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="2b57b-114">Se ad esempio si specifica 0x11110001, viene arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="2b57b-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="2b57b-115">Per completare il processo di firma di una DLL, utilizzare l' `–R` opzione dello strumento per la denominazione sicura (sn. exe).</span><span class="sxs-lookup"><span data-stu-id="2b57b-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="2b57b-116">Questa opzione viene ignorata se la destinazione non è una DLL.</span><span class="sxs-lookup"><span data-stu-id="2b57b-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="2b57b-117">Per impostare-baseaddress nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2b57b-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="2b57b-118">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="2b57b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2b57b-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2b57b-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2b57b-120">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="2b57b-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2b57b-121">3. fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="2b57b-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="2b57b-122">4. modificare il valore nella casella **indirizzo di base dll:** .</span><span class="sxs-lookup"><span data-stu-id="2b57b-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="2b57b-123">**Nota:**      **Indirizzo di base dll:** box è di sola lettura, a meno che la destinazione non sia una dll.</span><span class="sxs-lookup"><span data-stu-id="2b57b-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b57b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b57b-124">See also</span></span>

- [<span data-ttu-id="2b57b-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b57b-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2b57b-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b57b-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="2b57b-127">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="2b57b-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="2b57b-128">[Sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="2b57b-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
