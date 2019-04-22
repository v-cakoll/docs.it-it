---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 337fc1fb4dfc83c9b4814d3e45eb0cbe0758f7ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842525"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Errori durante la compilazione di XML schema nel progetto
Si sono verificati errori durante la compilazione di XML schema nel progetto. Per questo motivo, IntelliSense XML non è disponibile.  
  
 Si verifica un errore in uno schema di XML Schema Definition (XSD) incluso nel progetto. Questo errore si verifica quando si aggiunge un file di schema (XSD) di XSD che è in conflitto con lo schema XSD esistente impostato per il progetto.  
  
 **ID errore:** BC36810  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Fare doppio clic su avviso nella **elenco errori** finestra. Visual Basic verrà visualizzata la posizione nel file XSD che rappresenta l'origine dell'avviso. Correggere l'errore nello schema XSD.  
  
-   Assicurarsi che tutti i necessari file di schema (XSD) XSD sono inclusi nel progetto. Potrebbe essere necessario fare clic su **Mostra tutti i file** nel **Project** file menu per visualizzare il XSD **Esplora soluzioni**. Fare doppio clic su un file XSD e quindi fare clic su **Includi nel progetto** per includere il file nel progetto.  
  
-   Se si usa il codice XML alla procedura guidata Schema, questo errore può verificarsi se in grado di dedurre schemi più di una volta dalla stessa origine. In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo file XML al modello di elemento di Schema e quindi indicare il codice XML alla procedura guidata Schema con tutte le origini XML applicabile per il progetto.  
  
-   Se nessun errore è identificato nello schema XSD, il compilatore XML non dispone di informazioni sufficienti per fornire un messaggio di errore dettagliato. È possibile ottenere informazioni più dettagliate sugli errori, facendo in modo che gli spazi dei nomi XML per i file con estensione XSD incluso nel progetto corrispondano gli spazi dei nomi XML identificate per lo Schema XML, impostare in Visual Studio.  
  
## <a name="see-also"></a>Vedere anche

- [Finestra Elenco errori](/visualstudio/ide/reference/error-list-window)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
