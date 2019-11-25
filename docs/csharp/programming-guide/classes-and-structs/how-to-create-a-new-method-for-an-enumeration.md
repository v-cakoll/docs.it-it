---
title: Come creare un nuovo metodo per un'enumerazione- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 02af55c851392ce5dde4c83fd32d18b927950a3f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971036"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="4fcdc-102">Come creare un nuovo metodo per un'enumerazione (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="4fcdc-102">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="4fcdc-103">È possibile usare metodi di estensione per aggiungere la funzionalità specifica di un particolare tipo enum.</span><span class="sxs-lookup"><span data-stu-id="4fcdc-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fcdc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4fcdc-104">Example</span></span>  
 <span data-ttu-id="4fcdc-105">Nell'esempio seguente, l'enumerazione `Grades` rappresenta il voto che uno studente potrebbe ricevere in un corso.</span><span class="sxs-lookup"><span data-stu-id="4fcdc-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="4fcdc-106">Il metodo di estensione denominato `Passing` viene aggiunto al tipo `Grades` in modo che ogni istanza di tale tipo ora "sa" se rappresenta un voto sufficiente oppure no.</span><span class="sxs-lookup"><span data-stu-id="4fcdc-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="4fcdc-107">Si noti che la classe `Extensions` contiene anche una variabile statica aggiornata in modo dinamico e che il valore restituito dal metodo di estensione riflette il valore corrente di tale variabile.</span><span class="sxs-lookup"><span data-stu-id="4fcdc-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="4fcdc-108">Ciò dimostra che dietro le quinte i metodi di estensione vengono chiamati direttamente per la classe statica nella quale sono definiti.</span><span class="sxs-lookup"><span data-stu-id="4fcdc-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcdc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fcdc-109">See also</span></span>

- [<span data-ttu-id="4fcdc-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4fcdc-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4fcdc-111">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="4fcdc-111">Extension Methods</span></span>](./extension-methods.md)
