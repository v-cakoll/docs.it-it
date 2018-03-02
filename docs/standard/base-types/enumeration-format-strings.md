---
title: Stringhe di formato di enumerazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58004fa19f2ec3b1ca7570d6ca75702510148002
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="b1780-102">Stringhe di formato di enumerazione</span><span class="sxs-lookup"><span data-stu-id="b1780-102">Enumeration Format Strings</span></span>
<span data-ttu-id="b1780-103">È possibile usare il metodo <xref:System.Enum.ToString%2A?displayProperty=nameWithType> per creare un nuovo oggetto stringa che rappresenti il valore numerico, esadecimale o stringa di un membro di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b1780-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="b1780-104">Questo metodo accetta una delle stringhe di formattazione di enumerazione per specificare il valore che si vuole venga restituito.</span><span class="sxs-lookup"><span data-stu-id="b1780-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>  
  
 <span data-ttu-id="b1780-105">La tabella seguente elenca le stringhe di formattazione di enumerazione e i valori da esse restituiti.</span><span class="sxs-lookup"><span data-stu-id="b1780-105">The following table lists the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="b1780-106">In questi identificatori di formato non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b1780-106">These format specifiers are not case-sensitive.</span></span>  
  
| <span data-ttu-id="b1780-107">Stringa di formattazione</span><span class="sxs-lookup"><span data-stu-id="b1780-107">Format string</span></span> | <span data-ttu-id="b1780-108">Risultato</span><span class="sxs-lookup"><span data-stu-id="b1780-108">Result</span></span> |  
| ------------- | ------ |  
| <span data-ttu-id="b1780-109">G o g</span><span class="sxs-lookup"><span data-stu-id="b1780-109">G or g</span></span> | <span data-ttu-id="b1780-110">Visualizza la voce di enumerazione sotto forma di valore di stringa, se possibile; in caso contrario, visualizza il valore intero dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="b1780-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="b1780-111">Se l'enumerazione viene definita con l'attributo **Flags** impostato, i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b1780-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="b1780-112">Se l'attributo **Flags** non è impostato, verrà visualizzato un valore non valido come voce numerica.</span><span class="sxs-lookup"><span data-stu-id="b1780-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="b1780-113">L'esempio seguente illustra l'identificatore di formato G.</span><span class="sxs-lookup"><span data-stu-id="b1780-113">The following example illustrates the G format specifier.</span></span><br><br><span data-ttu-id="b1780-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="b1780-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span></span> |  
| <span data-ttu-id="b1780-115">F o f</span><span class="sxs-lookup"><span data-stu-id="b1780-115">F or f</span></span> | <span data-ttu-id="b1780-116">Visualizza la voce di enumerazione come valore di stringa, se possibile.</span><span class="sxs-lookup"><span data-stu-id="b1780-116">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="b1780-117">Se il valore può essere visualizzato interamente come somma delle voci nell'enumerazione (anche se l'attributo **Flags** è assente), i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b1780-117">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="b1780-118">Se non è possibile determinare completamente il valore sulla base delle voci di enumerazione, il valore verrà formattato sotto forma di valore intero.</span><span class="sxs-lookup"><span data-stu-id="b1780-118">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="b1780-119">L'esempio seguente illustra l'identificatore di formato F.</span><span class="sxs-lookup"><span data-stu-id="b1780-119">The following example illustrates the F format specifier.</span></span><br><br><span data-ttu-id="b1780-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="b1780-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span></span> |  
| <span data-ttu-id="b1780-121">D o d</span><span class="sxs-lookup"><span data-stu-id="b1780-121">D or d</span></span> | <span data-ttu-id="b1780-122">Visualizza la voce di enumerazione come valore intero nella rappresentazione più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="b1780-122">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="b1780-123">L'esempio seguente illustra l'identificatore di formato D.</span><span class="sxs-lookup"><span data-stu-id="b1780-123">The following example illustrates the D format specifier.</span></span><br><br><span data-ttu-id="b1780-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="b1780-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span></span> |  
| <span data-ttu-id="b1780-125">X o x</span><span class="sxs-lookup"><span data-stu-id="b1780-125">X or x</span></span> | <span data-ttu-id="b1780-126">Visualizza la voce di enumerazione come valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b1780-126">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="b1780-127">Il valore viene rappresentato con l'aggiunta di un numero di zeri iniziali sufficiente a raggiungere la lunghezza minima di otto cifre.</span><span class="sxs-lookup"><span data-stu-id="b1780-127">The value is represented with leading zeros as necessary, to ensure that the value is a minimum eight digits in length.</span></span> <span data-ttu-id="b1780-128">L'esempio seguente illustra l'identificatore di formato X.</span><span class="sxs-lookup"><span data-stu-id="b1780-128">The following example illustrates the X format specifier.</span></span><br /><br /> <span data-ttu-id="b1780-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="b1780-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span></span> |  
  
## <a name="example"></a><span data-ttu-id="b1780-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1780-130">Example</span></span>  
 <span data-ttu-id="b1780-131">L'esempio seguente definisce un'enumerazione denominata `Colors` costituita dalle tre voci `Red`, `Blue` e `Green`.</span><span class="sxs-lookup"><span data-stu-id="b1780-131">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 <span data-ttu-id="b1780-132">Dopo aver definito l'enumerazione è possibile dichiararne un'istanza nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="b1780-132">After the enumeration is defined, an instance can be declared in the following manner.</span></span>  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 <span data-ttu-id="b1780-133">Sarà quindi possibile usare il metodo `Color.ToString(System.String)` per visualizzare il valore di enumerazione in modi diversi, a seconda dell'identificatore di formato passato.</span><span class="sxs-lookup"><span data-stu-id="b1780-133">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b1780-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1780-134">See Also</span></span>  
 [<span data-ttu-id="b1780-135">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="b1780-135">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
