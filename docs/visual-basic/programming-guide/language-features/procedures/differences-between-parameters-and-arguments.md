---
title: Differenze tra parametri e argomenti
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: dd0a62b6567f3e74763b7f2e9b96803c193c7976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403356"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Differenze tra parametri e argomenti (Visual Basic)
Nella maggior parte dei casi, una routine deve avere alcune informazioni sulle circostanze in cui è stata chiamata. Una procedura che esegue attività ripetute o condivise USA informazioni diverse per ogni chiamata. Queste informazioni sono costituite da variabili, costanti ed espressioni passate alla procedura quando viene chiamata.  
  
 Per comunicare queste informazioni alla routine, la procedura definisce un *parametro*e il codice chiamante passa un *argomento* a tale parametro. È possibile considerare il parametro come uno spazio di parcheggio e l'argomento come automobile. Proprio come le diverse automobili possono parcheggiare in uno spazio di parcheggio in momenti diversi, il codice chiamante può passare un argomento diverso allo stesso parametro ogni volta che chiama la procedura.  
  
## <a name="parameters"></a>Parametri  
 Un *parametro* rappresenta un valore che la routine prevede di passare quando viene chiamato. La dichiarazione della stored procedure definisce i relativi parametri.  
  
 Quando si definisce una `Function` `Sub` routine o, si specifica un *elenco di parametri* racchiusi tra parentesi immediatamente dopo il nome della procedura. Per ogni parametro, è necessario specificare un nome, un tipo di dati e un meccanismo di passaggio ([ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md)). È anche possibile indicare che un parametro è facoltativo. Questo significa che non è necessario passare un valore al codice chiamante.  
  
 Il nome di ogni parametro funge da *variabile locale* nella procedura. Il nome del parametro viene usato allo stesso modo di qualsiasi altra variabile.  
  
## <a name="arguments"></a>Arguments  
 Un *argomento* rappresenta il valore passato a un parametro di routine quando si chiama la stored procedure. Il codice chiamante fornisce gli argomenti quando chiama la routine.  
  
 Quando si chiama una `Function` `Sub` routine o, si include un *elenco di argomenti* tra parentesi immediatamente dopo il nome della procedura. Ogni argomento corrisponde al parametro nella stessa posizione dell'elenco.  
  
 A differenza della definizione del parametro, gli argomenti non hanno nomi. Ogni argomento è un'espressione, che può contenere zero o più variabili, costanti e valori letterali. Il tipo di dati dell'espressione valutata deve in genere corrispondere al tipo di dati definito per il parametro corrispondente e, in ogni caso, deve essere convertibile nel tipo di parametro.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
