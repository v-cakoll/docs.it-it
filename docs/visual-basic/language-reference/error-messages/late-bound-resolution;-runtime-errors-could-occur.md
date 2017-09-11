---
title: Risoluzione con associazione tardiva; potrebbero verificarsi degli errori di runtime | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
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
ms.openlocfilehash: 3baf28a17077d255b42f38ade21ce6153c24e862
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="8ed87-102">Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ed87-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="8ed87-103">Un oggetto viene assegnato a una variabile dichiarata di tipo di [tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8ed87-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="8ed87-104">Quando si dichiara una variabile come `Object`, il compilatore deve eseguire *l'associazione tardiva*, che determina operazioni supplementari in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8ed87-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="8ed87-105">Espone inoltre l'applicazione a possibili errori di runtime.</span><span class="sxs-lookup"><span data-stu-id="8ed87-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="8ed87-106">Ad esempio, se si assegna un <xref:System.Windows.Forms.Form>per il `Object` variabile e si tenta di accedere il <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>proprietà, il runtime genera un <xref:System.MemberAccessException>perché la <xref:System.Windows.Forms.Form>classe non espone un `NameTable` proprietà.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="8ed87-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="8ed87-107">Se si dichiara la variabile di un tipo specifico, il compilatore può eseguire *associazione anticipata* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8ed87-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="8ed87-108">Ciò comporta un miglioramento delle prestazioni, controllo dell'accesso ai membri del tipo specifico e una migliore leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="8ed87-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="8ed87-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="8ed87-109">By default, this message is a warning.</span></span> <span data-ttu-id="8ed87-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8ed87-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8ed87-111">**ID errore:** BC42017</span><span class="sxs-lookup"><span data-stu-id="8ed87-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8ed87-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8ed87-112">To correct this error</span></span>  
  
-   <span data-ttu-id="8ed87-113">Se possibile, dichiarare la variabile di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="8ed87-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed87-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ed87-114">See Also</span></span>  
 <span data-ttu-id="8ed87-115">[Associazione anticipata e tardiva](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ed87-115">[Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="8ed87-116"> [Dichiarazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span><span class="sxs-lookup"><span data-stu-id="8ed87-116"> [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span></span>
