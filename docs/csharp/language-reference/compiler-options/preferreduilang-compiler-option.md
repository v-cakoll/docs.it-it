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
ms.openlocfilehash: d079441e91ff90bcc974564bbd7069e0548a7d77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575293"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="ead2b-102">-preferreduilang (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="ead2b-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="ead2b-103">Utilizzando l'opzione del compilatore `-preferreduilang`, è possibile specificare la lingua in cui tramite il compilatore C# viene visualizzato l'output, ad esempio i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="ead2b-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead2b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ead2b-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="ead2b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ead2b-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="ead2b-106">[Nome](/windows/desktop/Intl/language-names) della lingua da usare per l'output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ead2b-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ead2b-107">Note</span><span class="sxs-lookup"><span data-stu-id="ead2b-107">Remarks</span></span>  
 <span data-ttu-id="ead2b-108">È possibile utilizzare l'opzione del compilatore `-preferreduilang` per specificare la lingua che si desidera venga utilizzata dal compilatore C# per i messaggi di errore e altri output della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ead2b-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="ead2b-109">Se il Language Pack della lingua non è installato, viene utilizzata l'impostazione della lingua del sistema operativo e non viene segnalato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="ead2b-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="ead2b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ead2b-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead2b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ead2b-111">See also</span></span>

- [<span data-ttu-id="ead2b-112">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="ead2b-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
