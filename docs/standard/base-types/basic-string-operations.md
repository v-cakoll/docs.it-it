---
title: Operazioni di base su stringhe in .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7692251a00c712f93b649d4cd6fc153bb248f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567484"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="50bbc-102">Operazioni di base su stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="50bbc-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="50bbc-103">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50bbc-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="50bbc-104">I siti Web ad esempio rispondono spesso a un utente che si è appena connesso con un saluto specifico che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50bbc-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="50bbc-105">Nelle cassi <xref:System.String?displayProperty=nameWithType> e<xref:System.Text.StringBuilder?displayProperty=nameWithType> sono disponibili vari metodi che consentono una costruzione dinamica di stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="50bbc-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="50bbc-106">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="50bbc-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50bbc-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="50bbc-107">In This Section</span></span>  
 [<span data-ttu-id="50bbc-108">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="50bbc-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="50bbc-109">Descrive le operazioni di base per convertire gli oggetti in stringhe e combinare diverse stringhe.</span><span class="sxs-lookup"><span data-stu-id="50bbc-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="50bbc-110">Eliminazione di spazi iniziali e finali e rimozione di caratteri</span><span class="sxs-lookup"><span data-stu-id="50bbc-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="50bbc-111">Descrive come eliminare gli spazi iniziali o finali o rimuovere caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="50bbc-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="50bbc-112">Aggiunta di spaziatura interna alle stringhe</span><span class="sxs-lookup"><span data-stu-id="50bbc-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="50bbc-113">Viene descritto come inserire caratteri o spazi vuoti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="50bbc-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="50bbc-114">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="50bbc-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="50bbc-115">Descrive come confrontare il contenuto di due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="50bbc-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="50bbc-116">Modifica della combinazione di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="50bbc-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="50bbc-117">Descrive come modificare la combinazione di maiuscole e minuscole dei caratteri all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="50bbc-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="50bbc-118">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="50bbc-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="50bbc-119">Descrive come creare e modificare oggetti stringa dinamici con la classe <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="50bbc-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="50bbc-120">Procedura: Eseguire modifiche di base delle stringhe</span><span class="sxs-lookup"><span data-stu-id="50bbc-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="50bbc-121">Illustra l'uso delle operazioni di base su stringhe.</span><span class="sxs-lookup"><span data-stu-id="50bbc-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50bbc-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="50bbc-122">Related Sections</span></span>  
 [<span data-ttu-id="50bbc-123">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="50bbc-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="50bbc-124">Descrive come eseguire la conversione di un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="50bbc-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="50bbc-125">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="50bbc-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="50bbc-126">Descrive come formattare le stringhe usando gli specificatori del formato.</span><span class="sxs-lookup"><span data-stu-id="50bbc-126">Describes how to format strings using format specifiers.</span></span>
