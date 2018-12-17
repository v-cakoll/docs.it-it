---
title: Operazioni di base su stringhe in .NET
description: Informazioni sulle operazioni di base che è possibile eseguire sulle stringhe.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
author: rpetrusha
ms.author: ronpet
ms.custom: seadec18
ms.openlocfilehash: 8621e79ad6e305f3859dc269965ecd216081f695
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150680"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="0897c-103">Operazioni di base su stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="0897c-103">Basic String Operations in .NET</span></span>
<span data-ttu-id="0897c-104">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0897c-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="0897c-105">I siti Web ad esempio rispondono spesso a un utente che si è appena connesso con un saluto specifico che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0897c-105">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="0897c-106">Nelle cassi <xref:System.String?displayProperty=nameWithType> e<xref:System.Text.StringBuilder?displayProperty=nameWithType> sono disponibili vari metodi che consentono una costruzione dinamica di stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0897c-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="0897c-107">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="0897c-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0897c-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0897c-108">In This Section</span></span>  
 [<span data-ttu-id="0897c-109">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="0897c-109">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="0897c-110">Descrive le operazioni di base per convertire gli oggetti in stringhe e combinare diverse stringhe.</span><span class="sxs-lookup"><span data-stu-id="0897c-110">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="0897c-111">Eliminazione di spazi iniziali e finali e rimozione di caratteri</span><span class="sxs-lookup"><span data-stu-id="0897c-111">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="0897c-112">Descrive come eliminare gli spazi iniziali o finali o rimuovere caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="0897c-112">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="0897c-113">Aggiunta di spaziatura interna alle stringhe</span><span class="sxs-lookup"><span data-stu-id="0897c-113">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="0897c-114">Viene descritto come inserire caratteri o spazi vuoti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="0897c-114">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="0897c-115">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="0897c-115">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="0897c-116">Descrive come confrontare il contenuto di due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="0897c-116">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="0897c-117">Modifica della combinazione di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="0897c-117">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="0897c-118">Descrive come modificare la combinazione di maiuscole e minuscole dei caratteri all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="0897c-118">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="0897c-119">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="0897c-119">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="0897c-120">Descrive come creare e modificare oggetti stringa dinamici con la classe <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="0897c-120">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="0897c-121">Procedura: Eseguire modifiche di base delle stringhe</span><span class="sxs-lookup"><span data-stu-id="0897c-121">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="0897c-122">Illustra l'uso delle operazioni di base su stringhe.</span><span class="sxs-lookup"><span data-stu-id="0897c-122">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0897c-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0897c-123">Related Sections</span></span>  
 [<span data-ttu-id="0897c-124">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="0897c-124">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="0897c-125">Descrive come eseguire la conversione di un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="0897c-125">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="0897c-126">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="0897c-126">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="0897c-127">Descrive come formattare le stringhe usando gli specificatori del formato.</span><span class="sxs-lookup"><span data-stu-id="0897c-127">Describes how to format strings using format specifiers.</span></span>
