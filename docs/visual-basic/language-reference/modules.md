---
title: Moduli (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modules, Visual Basic
ms.assetid: 370bfc90-e8f2-4942-bdec-9897ce605d31
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 808510c83339e1768dba39f119a2e97ac44f0e4a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="modules-visual-basic"></a><span data-ttu-id="bb6b3-102">Moduli (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb6b3-102">Modules (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="bb6b3-103">offre diversi moduli che consentono di semplificare le attività comuni nel codice, tra cui la modifica di stringhe, l'esecuzione di calcoli matematici, recupero di informazioni di sistema, l'esecuzione di operazioni su file e directory e così via.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-103"> provides several modules that enable you to simplify common tasks in your code, including manipulating strings, performing mathematical calculations, getting system information, performing file and directory operations, and so on.</span></span> <span data-ttu-id="bb6b3-104">Nella tabella seguente elenca i moduli forniti da [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb6b3-104">The following table lists the modules provided by [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="bb6b3-105"><xref:Microsoft.VisualBasic.Constants></xref:Microsoft.VisualBasic.Constants></span><span class="sxs-lookup"><span data-stu-id="bb6b3-105"><xref:Microsoft.VisualBasic.Constants></span></span>|<span data-ttu-id="bb6b3-106">Sono disponibili varie costanti.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-106">Contains miscellaneous constants.</span></span> <span data-ttu-id="bb6b3-107">Queste costanti possono essere usate ovunque nel codice.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-107">These constants can be used anywhere in your code.</span></span>|  
|<span data-ttu-id="bb6b3-108"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="bb6b3-108"><xref:Microsoft.VisualBasic.ControlChars></span></span>|<span data-ttu-id="bb6b3-109">Contiene caratteri di controllo per la stampa e visualizzazione di testo.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-109">Contains constant control characters for printing and displaying text.</span></span>|  
|<span data-ttu-id="bb6b3-110"><xref:Microsoft.VisualBasic.Conversion></xref:Microsoft.VisualBasic.Conversion></span><span class="sxs-lookup"><span data-stu-id="bb6b3-110"><xref:Microsoft.VisualBasic.Conversion></span></span>|<span data-ttu-id="bb6b3-111">Contiene membri per la conversione di numeri decimali in altre basi, numeri in stringhe, le stringhe in numeri e dati di un tipo a altro.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-111">Contains members that convert decimal numbers to other bases, numbers to strings, strings to numbers, and one data type to another.</span></span>|  
|<span data-ttu-id="bb6b3-112"><xref:Microsoft.VisualBasic.DateAndTime></xref:Microsoft.VisualBasic.DateAndTime></span><span class="sxs-lookup"><span data-stu-id="bb6b3-112"><xref:Microsoft.VisualBasic.DateAndTime></span></span>|<span data-ttu-id="bb6b3-113">Contiene membri che ottenere la data corrente o l'ora, eseguono i calcoli di data, restituiscono una data o ora, impostare la data o ora o della durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-113">Contains members that get the current date or time, perform date calculations, return a date or time, set the date or time, or time the duration of a process.</span></span>|  
|<span data-ttu-id="bb6b3-114"><xref:Microsoft.VisualBasic.ErrObject></xref:Microsoft.VisualBasic.ErrObject></span><span class="sxs-lookup"><span data-stu-id="bb6b3-114"><xref:Microsoft.VisualBasic.ErrObject></span></span>|<span data-ttu-id="bb6b3-115">Contiene informazioni sui metodi per generare o cancellare un errore e di errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-115">Contains information about run-time errors and methods to raise or clear an error.</span></span>|  
|<span data-ttu-id="bb6b3-116"><xref:Microsoft.VisualBasic.FileSystem></xref:Microsoft.VisualBasic.FileSystem></span><span class="sxs-lookup"><span data-stu-id="bb6b3-116"><xref:Microsoft.VisualBasic.FileSystem></span></span>|<span data-ttu-id="bb6b3-117">Contiene membri che eseguono operazioni su file, directory o cartella e del sistema.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-117">Contains members that perform file, directory or folder, and system operations.</span></span>|  
|<span data-ttu-id="bb6b3-118"><xref:Microsoft.VisualBasic.Financial></xref:Microsoft.VisualBasic.Financial></span><span class="sxs-lookup"><span data-stu-id="bb6b3-118"><xref:Microsoft.VisualBasic.Financial></span></span>|<span data-ttu-id="bb6b3-119">Contiene le procedure utilizzate per eseguire calcoli finanziari.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-119">Contains procedures that are used to perform financial calculations.</span></span>|  
|<span data-ttu-id="bb6b3-120"><xref:Microsoft.VisualBasic.Globals></xref:Microsoft.VisualBasic.Globals></span><span class="sxs-lookup"><span data-stu-id="bb6b3-120"><xref:Microsoft.VisualBasic.Globals></span></span>|<span data-ttu-id="bb6b3-121">Contiene informazioni sulla versione del motore di script corrente.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-121">Contains information about the current scripting engine version.</span></span>|  
|<span data-ttu-id="bb6b3-122"><xref:Microsoft.VisualBasic.Information></xref:Microsoft.VisualBasic.Information></span><span class="sxs-lookup"><span data-stu-id="bb6b3-122"><xref:Microsoft.VisualBasic.Information></span></span>|<span data-ttu-id="bb6b3-123">Contiene i membri che restituiscono, testano o verificare le informazioni come dimensione della matrice, i nomi dei tipi e così via.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-123">Contains the members that return, test for, or verify information such as array size, type names, and so on.</span></span>|  
|<span data-ttu-id="bb6b3-124"><xref:Microsoft.VisualBasic.Interaction></xref:Microsoft.VisualBasic.Interaction></span><span class="sxs-lookup"><span data-stu-id="bb6b3-124"><xref:Microsoft.VisualBasic.Interaction></span></span>|<span data-ttu-id="bb6b3-125">Contiene membri che interagiscono con gli oggetti, applicazioni e sistemi.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-125">Contains members interact with objects, applications, and systems.</span></span>|  
|<span data-ttu-id="bb6b3-126"><xref:Microsoft.VisualBasic.Strings></xref:Microsoft.VisualBasic.Strings></span><span class="sxs-lookup"><span data-stu-id="bb6b3-126"><xref:Microsoft.VisualBasic.Strings></span></span>|<span data-ttu-id="bb6b3-127">Contiene membri che eseguono operazioni di stringa, ad esempio la formattazione di stringhe di ricerca di una stringa, ottenere la lunghezza di una stringa e così via.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-127">Contains members that perform string operations such as reformatting strings, searching a string, getting the length of a string, and so on.</span></span>|  
|<span data-ttu-id="bb6b3-128"><xref:Microsoft.VisualBasic.VBMath></xref:Microsoft.VisualBasic.VBMath></span><span class="sxs-lookup"><span data-stu-id="bb6b3-128"><xref:Microsoft.VisualBasic.VBMath></span></span>|<span data-ttu-id="bb6b3-129">Contiene i membri di eseguire operazioni matematiche.</span><span class="sxs-lookup"><span data-stu-id="bb6b3-129">Contains members perform mathematical operations.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb6b3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb6b3-130">See Also</span></span>  
 <span data-ttu-id="bb6b3-131">[Riferimenti al linguaggio Visual Basic](../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb6b3-131">[Visual Basic Language Reference](../../visual-basic/language-reference/index.md) </span></span>  
<span data-ttu-id="bb6b3-132"> [Visual Basic](../../visual-basic/index.md)</span><span class="sxs-lookup"><span data-stu-id="bb6b3-132"> [Visual Basic](../../visual-basic/index.md)</span></span>
