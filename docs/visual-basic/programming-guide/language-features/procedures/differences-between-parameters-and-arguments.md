---
title: Differenze tra parametri e argomenti (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6613c64a24ef18239422b69f8b5320eadc95b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Differenze tra parametri e argomenti (Visual Basic)
Nella maggior parte dei casi, una routine deve avere alcune informazioni sulle circostanze in cui è stato chiamato. Una routine che esegue attività ripetute o condivise utilizza informazioni diverse per ogni chiamata. Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla routine quando viene chiamato.  
  
 Per comunicare le informazioni per la procedura, la routine definisce un *parametro*, e il codice chiamante passa una *argomento* a tale parametro. È possibile considerare il parametro come spazio di parcheggio e l'argomento a un'automobile. Così come diverse automobili possono parcheggiare in uno spazio di parcheggio in momenti diversi, il codice chiamante può passare un argomento differente per lo stesso parametro ogni volta che si chiama la routine.  
  
## <a name="parameters"></a>Parametri  
 Oggetto *parametro* rappresenta un valore che la procedura prevede di passare al momento della chiamata. La dichiarazione della routine definisce i parametri.  
  
 Quando si definisce un `Function` o `Sub` procedura, si specifica un *elenco parametri* tra parentesi immediatamente dopo il nome della stored procedure. Per ogni parametro, specificare un nome, un tipo di dati e un meccanismo di passaggio ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). È anche possibile indicare che un parametro è facoltativo. Ciò significa che il codice chiamante non dispone di passare un valore per tale.  
  
 Il nome di ogni parametro viene utilizzato come un *variabile locale* nella procedura. Utilizzare il nome del parametro la stessa modalità di utilizzo di qualsiasi altra variabile.  
  
## <a name="arguments"></a>Argomenti  
 Un *argomento* rappresenta il valore passato a un parametro di procedura quando si chiama la routine. Il codice chiamante fornisce gli argomenti quando viene chiamata la procedura.  
  
 Quando si chiama un `Function` o `Sub` procedura, include un *elenco di argomenti* tra parentesi immediatamente dopo il nome della stored procedure. Ciascun argomento corrisponde al parametro nella stessa posizione nell'elenco.  
  
 A differenza di definizione dei parametri, argomenti non hanno nomi. Ogni argomento è un'espressione che può contenere zero o più variabili, costanti e valori letterali. Il tipo di dati dell'espressione valutata in genere deve corrispondere al tipo di dati definito per il parametro corrispondente, e in ogni caso deve essere convertibile nel tipo di parametro.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Procedura: Definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Routine ricorsive](./recursive-procedures.md)  
 [Overload della routine](./procedure-overloading.md)
