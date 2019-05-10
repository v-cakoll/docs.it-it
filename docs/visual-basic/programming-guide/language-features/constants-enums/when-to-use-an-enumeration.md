---
title: Quando utilizzare un'enumerazione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: a43c55d4ad6a895957b53ae18c3641c5383a24ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585068"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Quando utilizzare un'enumerazione (Visual Basic)
Le enumerazioni offrono un modo semplice per lavorare con i set di costanti correlate. Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori. Le enumerazioni sono considerate come tipi di dati e di utilizzarli per creare set di costanti per l'uso con le variabili e proprietà.  
  
## <a name="when-to-use-an-enumeration"></a>Quando utilizzare un'enumerazione  
 Ogni volta che una routine accetta un set limitato di variabili, è consigliabile usare un'enumerazione. Le enumerazioni rendono il codice più chiaro e leggibile, soprattutto quando vengono usati nomi significativi.  
  
 I vantaggi dell'uso di enumerazioni includono:  
  
- Consente di ridurre gli errori causati da trasporre o errata digitazione numeri.  
  
- Semplifica modificare i valori in futuro.  
  
- Rende il codice più leggibile, ciò significa che è meno probabile che gli errori al suo interno.  
  
- Assicura la compatibilità. Con le enumerazioni, quest'ultima è meno probabile che se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.  
  
## <a name="naming-enumerations"></a>Denominazione delle enumerazioni  
 Usare una convenzione di denominazione per i membri di enumerazione. Quando Visual Basic rileva un nome di membro di enumerazione, potrebbe essere generata un'eccezione se altre librerie dei tipi di riferimento contengono lo stesso nome. Usare un prefisso univoco che identifica i valori dall'applicazione o componente.  
  
 Quando si fa riferimento a un membro di enumerazione, è necessario qualificare il nome del membro con il nome di enumerazione o utilizzare il `Imports` istruzione. Per altre informazioni, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumerazioni predefinite  
 Visual Basic fornisce un numero di enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResult`, per semplificare il codice. Per un elenco di questi elementi, vedere [costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Procedura: Scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
