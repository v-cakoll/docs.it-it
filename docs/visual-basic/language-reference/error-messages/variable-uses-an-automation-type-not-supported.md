---
title: La variabile utilizza un tipo di automazione non supportato in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: d369930752989ff69ee17359e85118f3af4b70b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766890"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a><span data-ttu-id="60f1d-102">La variabile utilizza un tipo di automazione non supportato in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60f1d-102">Variable uses an Automation type not supported in Visual Basic</span></span>

<span data-ttu-id="60f1d-103">Si è provato a usare una variabile definita in una libreria dei tipi o una raccolta di oggetti con un tipo di dati non supportato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="60f1d-103">You tried to use a variable defined in a type library or object library that has a data type not supported by Visual Basic.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="60f1d-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="60f1d-104">To correct this error</span></span>

- <span data-ttu-id="60f1d-105">Usare una variabile di un tipo riconosciuto da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="60f1d-105">Use a variable of a type recognized by Visual Basic.</span></span>

     <span data-ttu-id="60f1d-106">-oppure-</span><span class="sxs-lookup"><span data-stu-id="60f1d-106">-or-</span></span>

- <span data-ttu-id="60f1d-107">Se si verifica questo errore quando si usa `FileGet` oppure `FileGetObject`, assicurarsi che il file si sta tentando di usare è stato scritto con `FilePut` o `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="60f1d-107">If you encounter this error while using `FileGet` or `FileGetObject`, make sure the file you are trying to use was written to with `FilePut` or `FilePutObject`.</span></span>

## <a name="see-also"></a><span data-ttu-id="60f1d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60f1d-108">See also</span></span>

- [<span data-ttu-id="60f1d-109">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="60f1d-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
