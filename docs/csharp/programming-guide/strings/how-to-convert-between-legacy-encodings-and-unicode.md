---
title: 'Procedura: eseguire la conversione tra codifiche legacy e Unicode (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="ddeb0-102">Procedura: eseguire la conversione tra codifiche legacy e Unicode (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ddeb0-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="ddeb0-103">In C#, tutte le stringhe in memoria sono codificate come Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="ddeb0-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="ddeb0-104">I dati trasferiti da un archivio a un oggetto `string` vengono automaticamente convertiti in UTF-16.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="ddeb0-105">Se i dati contengono solo valori ASCII compresi tra 0 e 127, non sono richieste operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="ddeb0-106">Se invece il testo di origine contiene valori in byte ASCII estesi (da 128 a 255), per impostazione predefinita i caratteri estesi saranno interpretati in base alla tabella codici corrente.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="ddeb0-107">Per specificare che il testo di origine deve essere interpretato in base a una tabella codici diversa, usare la classe <xref:System.Text.Encoding?displayProperty=fullName> come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddeb0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddeb0-108">Example</span></span>  
 <span data-ttu-id="ddeb0-109">L'esempio seguente mostra come convertire un file di testo con codifica ASCII a 8 bit, interpretando il testo di origine in base alla tabella codici 737 di Windows.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="ddeb0-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ddeb0-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeb0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddeb0-111">See Also</span></span>  
 [<span data-ttu-id="ddeb0-112">Stringhe</span><span class="sxs-lookup"><span data-stu-id="ddeb0-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

