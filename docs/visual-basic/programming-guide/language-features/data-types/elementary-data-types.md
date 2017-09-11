---
title: Tipi di dati elementari (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- elementary data types
- data types [Visual Basic], elementary
ms.assetid: dfad6fe9-2da6-49a4-b0b1-2d7ae0283de5
caps.latest.revision: 16
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
ms.openlocfilehash: 6d363fdd7f7f2755aec34dfe82e38d83ba6e56af
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="elementary-data-types-visual-basic"></a><span data-ttu-id="6dd1c-102">Tipi di dati elementari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dd1c-102">Elementary Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="6dd1c-103">fornisce un set di tipi di dati predefiniti che è possibile utilizzare per molti elementi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-103"> supplies a set of predefined data types, which you can use for many of your programming elements.</span></span> <span data-ttu-id="6dd1c-104">In questa sezione vengono descritti questi tipi e sul loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-104">This section describes these types and how to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dd1c-105">Ogni tipo di dati di base in Visual Basic è supportata da una struttura o una classe che è il <xref:System>dello spazio dei nomi.</xref:System></span><span class="sxs-lookup"><span data-stu-id="6dd1c-105">Every elementary data type in Visual Basic is supported by a structure or a class that is in the <xref:System> namespace.</span></span> <span data-ttu-id="6dd1c-106">Il compilatore utilizza ogni parola chiave tipo di dati come un alias per la struttura sottostante o classe.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-106">The compiler uses each data type keyword as an alias for the underlying structure or class.</span></span> <span data-ttu-id="6dd1c-107">Ad esempio, dichiarare una variabile utilizzando la parola riservata `Byte` quella della dichiarazione dello stesso usando il nome della struttura completo <xref:System.Byte?displayProperty=fullName>.</xref:System.Byte?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6dd1c-107">For example, declaring a variable by using the reserved word `Byte` is the same as declaring it by using the fully qualified structure name <xref:System.Byte?displayProperty=fullName>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dd1c-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6dd1c-108">In This Section</span></span>  
 [<span data-ttu-id="6dd1c-109">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="6dd1c-109">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 <span data-ttu-id="6dd1c-110">Descrive i tipi numerici integrali e non integrali.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-110">Describes the integral and non-integral numeric types.</span></span>  
  
 [<span data-ttu-id="6dd1c-111">Dati di tipo carattere</span><span class="sxs-lookup"><span data-stu-id="6dd1c-111">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 <span data-ttu-id="6dd1c-112">Viene descritto il `Char` e `String` tipi.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-112">Describes the `Char` and `String` types.</span></span>  
  
 [<span data-ttu-id="6dd1c-113">Tipi di dati vari</span><span class="sxs-lookup"><span data-stu-id="6dd1c-113">Miscellaneous Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 <span data-ttu-id="6dd1c-114">Viene descritto il `Boolean`, `Date`, e `Object` tipi.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-114">Describes the `Boolean`, `Date`, and `Object` types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6dd1c-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6dd1c-115">Related Sections</span></span>  
 [<span data-ttu-id="6dd1c-116">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6dd1c-116">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="6dd1c-117">Introduce il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati e viene descritto come utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="6dd1c-117">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="6dd1c-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6dd1c-118">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="6dd1c-119">Viene fornita una panoramica dei tipi di dati elementari forniti da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dd1c-119">Provides an overview of the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
