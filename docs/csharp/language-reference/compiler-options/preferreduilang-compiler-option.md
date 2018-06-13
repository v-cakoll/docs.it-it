---
title: -preferreduilang (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211751"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="6c634-102">-preferreduilang (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6c634-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="6c634-103">Utilizzando l'opzione del compilatore `-preferreduilang`, è possibile specificare la lingua in cui tramite il compilatore C# viene visualizzato l'output, ad esempio i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="6c634-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c634-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c634-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c634-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6c634-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="6c634-106">[Nome](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) della lingua da usare per l'output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6c634-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c634-107">Note</span><span class="sxs-lookup"><span data-stu-id="6c634-107">Remarks</span></span>  
 <span data-ttu-id="6c634-108">È possibile utilizzare l'opzione del compilatore `-preferreduilang` per specificare la lingua che si desidera venga utilizzata dal compilatore C# per i messaggi di errore e altri output della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6c634-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="6c634-109">Se il Language Pack della lingua non è installato, viene utilizzata l'impostazione della lingua del sistema operativo e non viene segnalato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="6c634-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="6c634-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c634-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c634-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c634-111">See Also</span></span>  
 [<span data-ttu-id="6c634-112">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="6c634-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
