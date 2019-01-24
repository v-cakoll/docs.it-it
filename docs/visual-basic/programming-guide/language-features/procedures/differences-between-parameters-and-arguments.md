---
title: Differenze tra parametri e argomenti (Visual Basic)
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
ms.openlocfilehash: ec7c92975bc056fd740033b602b15cd1611c44d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694035"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Differenze tra parametri e argomenti (Visual Basic)
Nella maggior parte dei casi, una routine deve avere alcune informazioni sulle circostanze in cui è stato chiamato. Una routine che esegue attività ripetute o condivise Usa informazioni diverse per ogni chiamata. Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla procedura quando si chiama.  
  
 Per comunicare le informazioni per la procedura, la routine definisce una *parametro*, e il codice chiamante passa un' *argomento* a tale parametro. È possibile pensare all'argomento come un'automobile e il parametro come uno spazio di parcheggio. Così come diverse automobili possono parcheggiare in uno spazio di parcheggio in momenti diversi, il codice chiamante può passare un argomento diverso per lo stesso parametro ogni volta che si chiama la routine.  
  
## <a name="parameters"></a>Parametri  
 Oggetto *parametro* rappresenta un valore che la procedura prevede che l'utente da passare al momento della chiamata. La dichiarazione della routine definisce i relativi parametri.  
  
 Quando si definisce un `Function` oppure `Sub` procedura, si specifica un *elenco di parametri* immediatamente dopo il nome della routine tra parentesi. Per ogni parametro, si specifica un nome di un tipo di dati e un meccanismo di passaggio ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). È anche possibile indicare che un parametro è facoltativo. Ciò significa che il codice chiamante non dispone di passare un valore per tale.  
  
 Il nome di ogni parametro viene utilizzato come un *variabile locale* nella procedura. Si usa il nome del parametro esattamente come si usa qualsiasi altra variabile.  
  
## <a name="arguments"></a>Argomenti  
 Un' *argomento* rappresenta il valore passato a un parametro di procedura quando si chiama la routine. Il codice chiamante fornisce gli argomenti quando viene chiamata la routine.  
  
 Quando si chiama un `Function` oppure `Sub` procedura, si include un *elenco di argomenti* immediatamente dopo il nome della routine tra parentesi. Ciascun argomento corrisponde al parametro nella stessa posizione nell'elenco.  
  
 A differenza di definizione dei parametri, gli argomenti non hanno nomi. Ogni argomento è un'espressione che può contenere zero o più variabili, costanti e letterali. Il tipo di dati dell'espressione valutata in genere deve corrispondere al tipo di dati definito per il parametro corrispondente, e in tutti i casi deve essere convertibile nel tipo di parametro.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
