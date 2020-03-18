---
title: Come definire le costanti in C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 15526655de8af6fed464376db1ac761468215210
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75337661"
---
# <a name="how-to-define-constants-in-c"></a>Come definire le costanti in C\#
Le costanti sono campi i cui valori vengono impostati in fase di compilazione e non possono mai essere modificati. Usare le costanti per specificare nomi significativi invece di valori letterali numerici ("numeri chiave") per valori particolari.  
  
> [!NOTE]
> In C# la direttiva per il preprocessore [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) non può essere usata per definire le costanti nel modo adottato in genere in C e C++.  
  
 Per definire valori costanti di tipi integrali (`int`, `byte` e così via) usare un tipo enumerato. Per altre informazioni, vedere [enum](../../language-reference/builtin-types/enum.md).  
  
 Per definire costanti non integrali, è possibile raggrupparle in una singola classe statica denominata `Constants`. A questo scopo sarà necessario che tutti i riferimenti alle costanti siano preceduti dal nome della classe, come illustrato nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 L'uso del qualificatore del nome della classe consente di fare in modo che tutti gli utenti che usano la costante comprendano che si tratta di una costante e che non può essere modificata.  
  
## <a name="see-also"></a>Vedere anche

- [Classi e struct](./index.md)
