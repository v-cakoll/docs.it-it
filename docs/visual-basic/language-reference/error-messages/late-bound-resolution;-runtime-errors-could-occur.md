---
title: Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 6b78dfed1d615ba865f136365eac1c9c131ed5a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661943"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="f2f48-102">Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f2f48-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="f2f48-103">Un oggetto viene assegnato a una variabile dichiarata di tipo i [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f2f48-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="f2f48-104">Quando si dichiara una variabile come `Object`, il compilatore deve eseguire *associazione tardiva*, in modo che operazioni supplementari in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f2f48-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="f2f48-105">Espone inoltre l'applicazione a possibili errori di runtime.</span><span class="sxs-lookup"><span data-stu-id="f2f48-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="f2f48-106">Ad esempio, se si assegna un <xref:System.Windows.Forms.Form> per il `Object` variabile e quindi tenta di accedere il <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> proprietà, il runtime genera una <xref:System.MemberAccessException> perché la <xref:System.Windows.Forms.Form> classe non espone un `NameTable` proprietà.</span><span class="sxs-lookup"><span data-stu-id="f2f48-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="f2f48-107">Se si dichiara la variabile di un tipo specifico, il compilatore può eseguire *associazione anticipata* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2f48-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="f2f48-108">Ciò comporta un miglioramento delle prestazioni, controllo dell'accesso ai membri del tipo specifico e una migliore leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="f2f48-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="f2f48-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="f2f48-109">By default, this message is a warning.</span></span> <span data-ttu-id="f2f48-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f2f48-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f2f48-111">**ID errore:** BC42017</span><span class="sxs-lookup"><span data-stu-id="f2f48-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2f48-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f2f48-112">To correct this error</span></span>  
  
- <span data-ttu-id="f2f48-113">Se possibile, dichiarare la variabile di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="f2f48-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f48-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2f48-114">See also</span></span>

- [<span data-ttu-id="f2f48-115">Associazione anticipata e tardiva</span><span class="sxs-lookup"><span data-stu-id="f2f48-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="f2f48-116">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f2f48-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
