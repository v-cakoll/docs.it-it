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
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a>Procedura: eseguire la conversione tra codifiche legacy e Unicode (Guida per programmatori C#)
In C#, tutte le stringhe in memoria sono codificate come Unicode (UTF-16). I dati trasferiti da un archivio a un oggetto `string` vengono automaticamente convertiti in UTF-16. Se i dati contengono solo valori ASCII compresi tra 0 e 127, non sono richieste operazioni aggiuntive. Se invece il testo di origine contiene valori in byte ASCII estesi (da 128 a 255), per impostazione predefinita i caratteri estesi saranno interpretati in base alla tabella codici corrente. Per specificare che il testo di origine deve essere interpretato in base a una tabella codici diversa, usare la classe <xref:System.Text.Encoding?displayProperty=fullName> come mostrato nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come convertire un file di testo con codifica ASCII a 8 bit, interpretando il testo di origine in base alla tabella codici 737 di Windows.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Stringhe](../../../csharp/programming-guide/strings/index.md)

