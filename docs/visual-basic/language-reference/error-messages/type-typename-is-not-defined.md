---
title: Tipo '<typename>' non definito
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 89e2d1d18b456c96f62d6b9ee1dd8dc9d41bf665
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386932"
---
# <a name="type-typename-is-not-defined"></a>Tipo '\<typename>' non definito
L'istruzione ha fatto riferimento a un tipo che non è stato definito. È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum` ,, `Structure` `Class` o `Interface` .  
  
 **ID errore:** BC30002  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Verificare che la definizione del tipo e il relativo riferimento usino entrambi la stessa ortografia.  
  
- Verificare che la definizione del tipo sia accessibile al riferimento. Se, ad esempio, il tipo si trova in un altro modulo ed è stato dichiarato `Private` , spostare la definizione del tipo nel modulo di riferimento o dichiararlo `Public` .  
  
- Verificare che lo spazio dei nomi del tipo non sia ridefinito all'interno del progetto. In caso contrario, utilizzare la `Global` parola chiave per qualificare completamente il nome del tipo. Se, ad esempio, un progetto definisce uno spazio dei nomi denominato `System` , <xref:System.Object?displayProperty=nameWithType> non è possibile accedere al tipo a meno che non sia completo con la `Global` parola chiave: `Global.System.Object` .  
  
- Se il tipo è definito, ma la libreria di oggetti o la libreria dei tipi in cui è definita non è registrata in Visual Basic, fare clic su **Aggiungi riferimento** nel menu **progetto** , quindi selezionare la libreria di oggetti o la libreria dei tipi appropriata.  
  
- Verificare che il tipo si trovi in un assembly che fa parte del profilo di .NET Framework di destinazione. Per altre informazioni, vedere [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Vedere anche

- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Istruzione Enum](../statements/enum-statement.md)
- [Istruzione Structure](../statements/structure-statement.md)
- [Istruzione Class](../statements/class-statement.md)
- [Istruzione Interface](../statements/interface-statement.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
