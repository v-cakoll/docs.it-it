---
title: Operazioni di base su stringhe in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f241b99f97cad081a65fd8654169e444a1b588cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="34ba9-102">Operazioni di base su stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="34ba9-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="34ba9-103">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34ba9-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="34ba9-104">I siti Web ad esempio rispondono spesso a un utente che si è appena connesso con un saluto specifico che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34ba9-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="34ba9-105">Diversi metodi di <xref:System.String?displayProperty=nameWithType> e <xref:System.Text.StringBuilder?displayProperty=nameWithType> classi consentono di costruire dinamicamente stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="34ba9-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="34ba9-106">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="34ba9-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34ba9-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="34ba9-107">In This Section</span></span>  
 [<span data-ttu-id="34ba9-108">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="34ba9-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="34ba9-109">Descrive le operazioni di base per convertire gli oggetti in stringhe e combinare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="34ba9-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="34ba9-110">Eliminazione di spazi iniziali e finali e rimozione di caratteri</span><span class="sxs-lookup"><span data-stu-id="34ba9-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="34ba9-111">Viene descritto come tagliare o rimuovere i caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="34ba9-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="34ba9-112">Aggiunta di spaziatura interna alle stringhe</span><span class="sxs-lookup"><span data-stu-id="34ba9-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="34ba9-113">Viene descritto come inserire caratteri o spazi vuoti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="34ba9-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="34ba9-114">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="34ba9-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="34ba9-115">Viene descritto come confrontare il contenuto di due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="34ba9-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="34ba9-116">Modifica della combinazione di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="34ba9-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="34ba9-117">Viene descritto come modificare le minuscole dei caratteri all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="34ba9-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="34ba9-118">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="34ba9-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="34ba9-119">Viene descritto come creare e modificare oggetti stringa dinamici con il <xref:System.Text.StringBuilder> classe.</span><span class="sxs-lookup"><span data-stu-id="34ba9-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="34ba9-120">Procedura: Eseguire modifiche di base delle stringhe</span><span class="sxs-lookup"><span data-stu-id="34ba9-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="34ba9-121">Viene illustrato l'utilizzo di operazioni di base su stringhe.</span><span class="sxs-lookup"><span data-stu-id="34ba9-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="34ba9-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="34ba9-122">Related Sections</span></span>  
 [<span data-ttu-id="34ba9-123">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="34ba9-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="34ba9-124">Viene descritto come convertire un tipo in un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="34ba9-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="34ba9-125">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="34ba9-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="34ba9-126">Viene descritto come formattare le stringhe utilizzando gli identificatori di formato.</span><span class="sxs-lookup"><span data-stu-id="34ba9-126">Describes how to format strings using format specifiers.</span></span>
