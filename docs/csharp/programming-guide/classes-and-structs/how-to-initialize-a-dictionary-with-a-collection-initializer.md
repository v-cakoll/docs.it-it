---
title: 'Procedura: Inizializzare un dizionario con un inizializzatore di raccolta (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: b8c44ebbdc89d72398c3380d708b45d0b7dfdad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324174"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Procedura: Inizializzare un dizionario con un inizializzatore di raccolta (Guida per programmatori C#)
Un oggetto <xref:System.Collections.Generic.Dictionary`2> contiene una raccolta di coppie chiave-valore. Il relativo metodo <xref:System.Collections.Generic.Dictionary`2.Add*> accetta due parametri, uno per la chiave e uno per il valore. Per inizializzare un oggetto <xref:System.Collections.Generic.Dictionary`2> o qualsiasi raccolta il cui metodo `Add` accetta più parametri, racchiudere ogni set di parametri tra parentesi graffe, come illustrato nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, viene inizializzato un oggetto <xref:System.Collections.Generic.Dictionary`2> con istanze di tipo `StudentName`.  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Si noti che vi sono due coppie di parentesi graffe in ogni elemento della raccolta. Le parentesi più interne racchiudono l'inizializzatore di oggetto per `StudentName`, quelle più esterne racchiudono l'inizializzatore per la coppia chiave/valore che verrà aggiunta a `students`<xref:System.Collections.Generic.Dictionary`2>. Infine, tutto l'inizializzatore di insieme per il dizionario è racchiuso tra parentesi graffe.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in Visual Studio. Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], e ha un riferimento a System.Core.dll e una direttiva using per System.Linq. Se uno o più di questi requisiti non è presente nel progetto, è possibile aggiungerlo manualmente.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
