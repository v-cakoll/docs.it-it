---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352379"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="18314-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18314-102">-out (Visual Basic)</span></span>
<span data-ttu-id="18314-103">Specifica il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="18314-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18314-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18314-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="18314-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18314-105">Arguments</span></span>  
  
|<span data-ttu-id="18314-106">Termine</span><span class="sxs-lookup"><span data-stu-id="18314-106">Term</span></span>|<span data-ttu-id="18314-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="18314-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="18314-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="18314-108">Required.</span></span> <span data-ttu-id="18314-109">Nome del file di output creato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="18314-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="18314-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="18314-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18314-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="18314-111">Remarks</span></span>  
 <span data-ttu-id="18314-112">Specificare il nome completo e l'estensione del file da creare.</span><span class="sxs-lookup"><span data-stu-id="18314-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="18314-113">In caso contrario, il file con estensione exe prende il nome dal file del codice sorgente contenente la `Sub Main` stored procedure e il file con estensione dll prende il nome dal primo file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="18314-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="18314-114">Se si specifica un nome di file senza estensione exe o dll, il compilatore aggiunge automaticamente l'estensione, a seconda del valore specificato per l' `-target` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="18314-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="18314-115">Per impostare il Integrated Development Environment in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18314-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="18314-116">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="18314-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="18314-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18314-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="18314-118">2. fare clic sulla scheda **applicazione** .</span><span class="sxs-lookup"><span data-stu-id="18314-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="18314-119">3. modificare il valore nella casella **nome assembly** .</span><span class="sxs-lookup"><span data-stu-id="18314-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18314-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="18314-120">Example</span></span>  
 <span data-ttu-id="18314-121">Il codice seguente compila `T2.vb` e crea il file `T2.exe`di output.</span><span class="sxs-lookup"><span data-stu-id="18314-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="18314-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="18314-122">See also</span></span>

- [<span data-ttu-id="18314-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18314-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="18314-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18314-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="18314-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="18314-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
