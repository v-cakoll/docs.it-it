---
title: -preferreduilang (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a96a054b3d1f73b0fee209557388f7ea213ebbe9
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="preferreduilang-c-compiler-options"></a><span data-ttu-id="830e8-102">/preferreduilang (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="830e8-102">/preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="830e8-103">Utilizzando l'opzione del compilatore `/preferreduilang`, è possibile specificare la lingua in cui tramite il compilatore C# viene visualizzato l'output, ad esempio i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="830e8-103">By using the `/preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="830e8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="830e8-104">Syntax</span></span>  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="830e8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="830e8-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="830e8-106">[Nome](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) della lingua da usare per l'output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="830e8-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="830e8-107">Note</span><span class="sxs-lookup"><span data-stu-id="830e8-107">Remarks</span></span>  
 <span data-ttu-id="830e8-108">È possibile utilizzare l'opzione del compilatore `/preferreduilang` per specificare la lingua che si desidera venga utilizzata dal compilatore C# per i messaggi di errore e altri output della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="830e8-108">You can use the `/preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="830e8-109">Se il Language Pack della lingua non è installato, viene utilizzata l'impostazione della lingua del sistema operativo e non viene segnalato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="830e8-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="830e8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="830e8-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830e8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="830e8-111">See Also</span></span>  
 [<span data-ttu-id="830e8-112">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="830e8-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
