---
title: Quando utilizzare un'enumerazione
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353952"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Quando utilizzare un'enumerazione (Visual Basic)
Le enumerazioni offrono un modo semplice per usare set di costanti correlate. Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori. Le enumerazioni vengono considerate come tipi di dati ed è possibile utilizzarle per creare set di costanti da utilizzare con le variabili e le proprietà.  
  
## <a name="when-to-use-an-enumeration"></a>Quando utilizzare un'enumerazione  
 Ogni volta che una routine accetta un set limitato di variabili, è consigliabile utilizzare un'enumerazione. Le enumerazioni rendono il codice più chiaro e leggibile, in particolare quando vengono utilizzati nomi significativi.  
  
 I vantaggi dell'utilizzo delle enumerazioni includono:  
  
- Riduce gli errori causati dalla trasposizione o dalla digitazione errata dei numeri.  
  
- Semplifica la modifica dei valori in futuro.  
  
- Semplifica la lettura del codice, il che significa che è meno probabile che si verifichino errori.  
  
- Garantisce la compatibilità con le edizioni. Con le enumerazioni, è meno probabile che il codice abbia esito negativo se in futuro qualcuno modifica i valori corrispondenti ai nomi dei membri.  
  
## <a name="naming-enumerations"></a>Enumerazioni di denominazione  
 Usare una convenzione di denominazione per i membri dell'enumerazione. Quando Visual Basic rileva il nome di un membro di enumerazione, è possibile che venga generata un'eccezione se altre librerie dei tipi a cui viene fatto riferimento contengono lo stesso nome. Usare un prefisso univoco che identifichi i valori dell'applicazione o del componente.  
  
 Quando si fa riferimento a un membro di un'enumerazione, è necessario qualificare il nome del membro con il nome dell'enumerazione. in caso contrario, utilizzare l'istruzione `Imports`. Per altre informazioni, vedere [enumerazioni e qualificazione del nome](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumerazioni predefinite  
 Visual Basic fornisce alcune enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResult`, per semplificare il codice. Per un elenco di questi [, vedere costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
