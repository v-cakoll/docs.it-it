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
ms.openlocfilehash: a1fbbb8415e5e3405f039489aa071b0624065a9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405891"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="de04b-102">-preferreduilang (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="de04b-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="de04b-103">Utilizzando l'opzione del compilatore `-preferreduilang`, è possibile specificare la lingua in cui tramite il compilatore C# viene visualizzato l'output, ad esempio i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="de04b-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de04b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de04b-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="de04b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="de04b-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="de04b-106">[Nome](/windows/desktop/Intl/language-names) della lingua da usare per l'output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="de04b-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de04b-107">Note</span><span class="sxs-lookup"><span data-stu-id="de04b-107">Remarks</span></span>  
 <span data-ttu-id="de04b-108">È possibile utilizzare l'opzione del compilatore `-preferreduilang` per specificare la lingua che si desidera venga utilizzata dal compilatore C# per i messaggi di errore e altri output della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="de04b-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="de04b-109">Se il Language Pack della lingua non è installato, viene utilizzata l'impostazione della lingua del sistema operativo e non viene segnalato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="de04b-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="de04b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de04b-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de04b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de04b-111">See Also</span></span>

- [<span data-ttu-id="de04b-112">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="de04b-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
