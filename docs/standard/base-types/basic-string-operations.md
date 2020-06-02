---
title: Operazioni di base su stringhe in .NET
description: Informazioni sulle operazioni di base che è possibile eseguire sulle stringhe.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 8c19f6bcbdf5e4829c91aee1e2fd631537ed2e0a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277752"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="80ad4-103">Operazioni di base sulle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="80ad4-103">Basic string operations in .NET</span></span>

<span data-ttu-id="80ad4-104">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="80ad4-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="80ad4-105">Ad esempio, non è insolito che i siti Web rispondano a un utente appena connesso con un saluto specifico che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="80ad4-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="80ad4-106">Nelle cassi <xref:System.String?displayProperty=nameWithType> e<xref:System.Text.StringBuilder?displayProperty=nameWithType> sono disponibili vari metodi che consentono una costruzione dinamica di stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="80ad4-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="80ad4-107">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="80ad4-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="80ad4-108">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="80ad4-108">Related sections</span></span>

<span data-ttu-id="80ad4-109">[Conversione di tipi in .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="80ad4-109">[Type Conversion in .NET](type-conversion.md)</span></span>\
<span data-ttu-id="80ad4-110">Descrive come eseguire la conversione di un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="80ad4-110">Describes how to convert one type into another type.</span></span>  

<span data-ttu-id="80ad4-111">[Formattazione di tipi](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="80ad4-111">[Formatting Types](formatting-types.md)</span></span>\
<span data-ttu-id="80ad4-112">Descrive come formattare le stringhe usando gli specificatori del formato.</span><span class="sxs-lookup"><span data-stu-id="80ad4-112">Describes how to format strings using format specifiers.</span></span>
