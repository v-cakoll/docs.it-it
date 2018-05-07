---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Errori durante la compilazione di XML schema nel progetto
Si sono verificati errori durante la compilazione di XML schema nel progetto. Per questo motivo, IntelliSense XML non è disponibile.  
  
 Si verifica un errore in uno schema di XML Schema Definition (XSD) incluso nel progetto. Questo errore si verifica quando si aggiunge un file di schema (XSD) XSD che è in conflitto con lo schema XSD esistente impostato per il progetto.  
  
 **ID errore:** BC36810  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Fare doppio clic su avviso nel **elenco degli errori** finestra. Visual Basic verrà visualizzata la posizione nel file XSD che rappresenta l'origine dell'avviso. Per correggere l'errore nello schema XSD.  
  
-   Verificare che tutti i necessari file di schema (XSD) XSD sono inclusi nel progetto. Potrebbe essere necessario fare clic su **Mostra tutti i file** sul **progetto** menu per visualizzare il XSD file **Esplora**. Fare doppio clic su un file XSD e quindi fare clic su **Includi nel progetto** per includere il file nel progetto.  
  
-   Se si utilizza il codice XML per la procedura guidata Schema, questo errore può verificarsi se si dedurre schemi più volte la stessa origine. In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo codice XML per il modello di elemento di Schema e quindi indicare il codice XML per la procedura guidata Schema con tutte le origini XML applicabili per il progetto.  
  
-   Se nello schema XSD non viene identificato alcun errore, il compilatore XML non dispone di informazioni sufficienti per fornire un messaggio di errore dettagliato. È possibile ottenere informazioni dettagliate sull'errore, facendo in modo che gli spazi dei nomi XML per i file XSD incluso nel progetto corrispondano gli spazi dei nomi XML identificati per lo Schema XML, impostare in Visual Studio.  
  
## <a name="see-also"></a>Vedere anche  
 [Finestra Elenco errori](/visualstudio/ide/reference/error-list-window)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
