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
ms.openlocfilehash: 2ce1b148a2b1605b5b1283bdc3398409661f3f83
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523983"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="35ca6-103">Operazioni di base sulle stringhe in .NETBasic string operations in .NET</span><span class="sxs-lookup"><span data-stu-id="35ca6-103">Basic string operations in .NET</span></span>

<span data-ttu-id="35ca6-104">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="35ca6-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="35ca6-105">Ad esempio, non è raro che i siti Web rispondano a un utente appena connesso con un messaggio di saluto specializzato che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="35ca6-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="35ca6-106">Nelle cassi <xref:System.String?displayProperty=nameWithType> e<xref:System.Text.StringBuilder?displayProperty=nameWithType> sono disponibili vari metodi che consentono una costruzione dinamica di stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="35ca6-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="35ca6-107">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="35ca6-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="35ca6-108">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="35ca6-108">Related sections</span></span>

<span data-ttu-id="35ca6-109">[Conversione dei tipi in .NETType Conversion in .NET](../../../docs/standard/base-types/type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="35ca6-109">[Type Conversion in .NET](../../../docs/standard/base-types/type-conversion.md)</span></span>\
<span data-ttu-id="35ca6-110">Descrive come eseguire la conversione di un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="35ca6-110">Describes how to convert one type into another type.</span></span>  

<span data-ttu-id="35ca6-111">[Formattazione dei tipi](../../../docs/standard/base-types/formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="35ca6-111">[Formatting Types](../../../docs/standard/base-types/formatting-types.md)</span></span>\
<span data-ttu-id="35ca6-112">Descrive come formattare le stringhe usando gli specificatori del formato.</span><span class="sxs-lookup"><span data-stu-id="35ca6-112">Describes how to format strings using format specifiers.</span></span>
