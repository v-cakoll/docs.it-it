---
title: Operazioni di base su stringhe
description: Operazioni di base su stringhe
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9658098d-de60-4868-ba5b-0c278748a90f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b8bdbeccd226c412e725200fcaf81ec568afc5bc
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="basic-string-operations"></a><span data-ttu-id="c9ff8-104">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="c9ff8-104">Basic string operations</span></span>

<span data-ttu-id="c9ff8-105">Le applicazioni spesso interagiscono con gli utenti creando messaggi in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-105">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="c9ff8-106">I siti Web ad esempio rispondono spesso a un utente che si è appena connesso con un saluto specifico che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-106">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="c9ff8-107">Nelle cassi [System. String](xref:System.String) e [System.Text.StringBuilder](xref:System.Text.StringBuilder) sono disponibili vari metodi che consentono una costruzione dinamica di stringhe personalizzate da visualizzare nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-107">Several methods in the [System.String](xref:System.String) and [System.Text.StringBuilder](xref:System.Text.StringBuilder) classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="c9ff8-108">Questi metodi consentono anche di eseguire una serie di operazioni di base sulle stringhe, come la creazione di nuove stringhe partendo da matrici di byte, il confronto di valori di stringhe e la modifica di stringhe esistenti.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-108">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c9ff8-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c9ff8-109">In This Section</span></span>

<span data-ttu-id="c9ff8-110">[Creazione di nuove stringhe](creating-new.md): vengono descritte le operazioni di base per convertire gli oggetti in stringhe e combinare diverse stringhe.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-110">[Creating new strings](creating-new.md) - Describes basic ways to convert objects into strings and to combine strings.</span></span>

<span data-ttu-id="c9ff8-111">[Eliminazione di spazi iniziali e finali e rimozione di caratteri](trimming.md): viene descritto come eliminare gli spazi iniziali o finali o rimuovere caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-111">[Trimming and removing characters](trimming.md) - Describes how to trim or remove characters in a string.</span></span> 

<span data-ttu-id="c9ff8-112">[Aggiunta di spaziatura interna alle stringhe ](padding.md): viene descritto come inserire caratteri o spazi vuoti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-112">[Padding strings](padding.md) - Describes how to insert characters or empty spaces into a string.</span></span>

<span data-ttu-id="c9ff8-113">[Confronto di stringhe](comparing.md): viene descritto come confrontare il contenuto di due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-113">[Comparing strings](comparing.md) - Describes how to compare the contents of two or more strings.</span></span>

<span data-ttu-id="c9ff8-114">[Modifica della combinazione di maiuscole e minuscole](changing-case.md): viene descritto come modificare la combinazione di maiuscole e minuscole dei caratteri all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-114">[Changing case](changing-case.md) - Describes how to change the case of characters within a string.</span></span>

<span data-ttu-id="c9ff8-115">[Uso della classe StringBuilder](stringbuilder.md): viene descritto come creare e modificare oggetti stringa dinamici tramite la classe [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="c9ff8-115">[Using the StringBuilder class](stringbuilder.md) - Describes how to create and modify dynamic string objects with the [StringBuilder](xref:System.Text.StringBuilder) class.</span></span>

<span data-ttu-id="c9ff8-116">[Procedura: Eseguire modifiche di base delle stringhe](basic-manipulations.md): viene descritto l'uso delle operazioni di base relativo alle stringhe.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-116">[How to: Perform basic string manipulations](basic-manipulations.md) - Demonstrates the use of basic string operations.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c9ff8-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c9ff8-117">Related Sections</span></span>

<span data-ttu-id="c9ff8-118">[Conversione di tipi](type-conversion.md): viene descritto come convertire un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-118">[Type conversion](type-conversion.md) - Describes how to convert from one type to another.</span></span>

<span data-ttu-id="c9ff8-119">[Formattazione di tipi](formatting-types.md): viene descritto come formattare le stringhe usando gli specificatori del formato stringa.</span><span class="sxs-lookup"><span data-stu-id="c9ff8-119">[Formatting types](formatting-types.md) - Describes how to format strings using the string format specifiers.</span></span>



