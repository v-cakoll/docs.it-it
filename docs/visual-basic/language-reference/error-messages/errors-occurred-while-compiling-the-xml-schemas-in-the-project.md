---
title: Errori durante la compilazione di XML schema nel progetto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 919c6873ba63addb776d756a58c44a3fe3f0ec3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409628"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Errori durante la compilazione di XML schema nel progetto
Si sono verificati errori durante la compilazione degli XML Schema nel progetto. Per questo motivo, IntelliSense XML non è disponibile.  
  
 Si è verificato un errore in uno schema XSD (XML Schema Definition) incluso nel progetto. Questo errore si verifica quando si aggiunge un file di schema XSD (XSD) in conflitto con il set di schemi XSD esistente per il progetto.  
  
 **ID errore:** BC36810  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Fare doppio clic sull'avviso nella finestra **Elenco errori** . Visual Basic consentirà di passare al percorso nel file XSD che rappresenta l'origine dell'avviso. Correggere l'errore nello schema XSD.  
  
- Verificare che tutti i file di schema XSD (. xsd) necessari siano inclusi nel progetto. Potrebbe essere necessario fare clic su **Mostra tutti i file** nel menu **progetto** per visualizzare i file con estensione XSD in **Esplora soluzioni**. Fare clic con il pulsante destro del mouse su un file con estensione XSD, quindi scegliere **Includi nel progetto** per includere il file nel progetto.  
  
- Se si utilizza la procedura guidata XML per schema, questo errore può verificarsi se si deduce più di una volta gli schemi dalla stessa origine. In questo caso, è possibile rimuovere i file di schema XSD esistenti dal progetto, aggiungere un nuovo modello di elemento XML a schema, quindi fornire la procedura guidata XML to schema con tutte le origini XML applicabili per il progetto.  
  
- Se nello schema XSD non viene identificato alcun errore, è possibile che il compilatore XML non disponga di informazioni sufficienti per fornire un messaggio di errore dettagliato. Se si verifica che gli spazi dei nomi XML per i file XSD inclusi nel progetto corrispondano agli spazi dei nomi XML identificati per il set di XML Schema in Visual Studio, è possibile ottenere informazioni più dettagliate sugli errori.  
  
## <a name="see-also"></a>Vedere anche

- [Finestra Elenco errori](/visualstudio/ide/reference/error-list-window)
- [XML](../../programming-guide/language-features/xml/index.md)
