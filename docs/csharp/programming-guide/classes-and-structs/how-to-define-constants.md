---
title: 'Procedura: Definire costanti in C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 26d46335df3333379d5577a5c21a85a39eb6e43a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713199"
---
# <a name="how-to-define-constants-in-c"></a>Procedura: Definire costanti in C#
Le costanti sono campi i cui valori vengono impostati in fase di compilazione e non possono mai essere modificati. Usare le costanti per specificare nomi significativi invece di valori letterali numerici ("numeri chiave") per valori particolari.  
  
> [!NOTE]
>  In C# la direttiva per il preprocessore [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) non può essere usata per definire le costanti nel modo adottato in genere in C e C++.  
  
 Per definire valori costanti di tipi integrali (`int`, `byte` e così via) usare un tipo enumerato. Per altre informazioni, vedere [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Per definire costanti non integrali, è possibile raggrupparle in una singola classe statica denominata `Constants`. A questo scopo sarà necessario che tutti i riferimenti alle costanti siano preceduti dal nome della classe, come illustrato nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 L'uso del qualificatore del nome della classe consente di fare in modo che tutti gli utenti che usano la costante comprendano che si tratta di una costante e che non può essere modificata.  
  
## <a name="see-also"></a>Vedere anche

- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)
