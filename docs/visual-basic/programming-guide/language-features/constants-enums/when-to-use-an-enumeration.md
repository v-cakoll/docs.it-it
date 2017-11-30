---
title: Quando utilizzare un'enumerazione (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Quando utilizzare un'enumerazione (Visual Basic)
Enumerazioni offrono un modo semplice per utilizzare i set di costanti correlate. Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori. Le enumerazioni sono considerate come tipi di dati e utilizzarli per creare set di costanti per l'utilizzo con variabili e proprietà.  
  
## <a name="when-to-use-an-enumeration"></a>Quando utilizzare un'enumerazione  
 Ogni volta che una stored procedure accetta un set limitato di variabili, è possibile utilizzare un'enumerazione. Le enumerazioni rendono il codice più chiaro e più leggibile, soprattutto quando vengono utilizzati nomi significativi.  
  
 I vantaggi dell'utilizzo di enumerazioni includono:  
  
-   Per ridurre gli errori causati dalla trasposizione o numeri di errori di digitazione.  
  
-   Consente di modificare i valori in futuro.  
  
-   Rende il codice più facile da leggere, pertanto che è meno probabile che gli errori al suo interno.  
  
-   Garantisce la compatibilità. Con enumerazioni, il codice è meno probabile che se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.  
  
## <a name="naming-enumerations"></a>Denominazione delle enumerazioni  
 Utilizzare una convenzione di denominazione per i membri di enumerazione. Quando [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene rilevato un nome di membro di enumerazione, potrebbe essere generata un'eccezione se altre librerie dei tipi di riferimento contengono lo stesso nome. Utilizzare un prefisso univoco che identifica i valori di un'applicazione o componente.  
  
 Quando si fa riferimento a un membro di enumerazione, è necessario qualificare il nome del membro con il nome di enumerazione o utilizzare il `Imports` istruzione. Per ulteriori informazioni, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumerazioni predefinite  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce un numero di enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResult`, per semplificare il codice. Per un elenco di tali vedere [costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
