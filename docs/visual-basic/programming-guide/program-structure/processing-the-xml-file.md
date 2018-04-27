---
title: Elaborazione del file XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86dae99f2d17a506a27cf491a76083df618ba27b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="processing-the-xml-file-visual-basic"></a>Elaborazione del file XML (Visual Basic)
Il compilatore genera una stringa identificativa (ID) per ciascun costrutto del codice che contiene tag per la creazione della documentazione. (Per informazioni su come contrassegnare il codice, vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) La stringa ID identifica in modo univoco il costrutto. I programmi che elaborano il file XML è possono utilizzare la stringa di ID per identificare il corrispondente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] elemento metadati/reflection.  
  
 Il file XML non è una rappresentazione gerarchica del codice. è un elenco semplice con un ID generato per ogni elemento.  
  
 Per generare gli ID, il compilatore applica le regole seguenti:  
  
-   Nessuno spazio vuoto viene inserito nella stringa.  
  
-   La prima parte della stringa di ID identifica il tipo di membro specificato, con un singolo carattere seguito da due punti. Vengono utilizzati i seguenti tipi di membro.  
  
|Carattere|Descrizione|  
|---|---|  
|N|namespace<br /><br /> È possibile aggiungere commenti di documentazione a uno spazio dei nomi, ma è possibile creare riferimenti CREF ad essi, in cui è supportato.|  
|T|tipo: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|campo: `Dim`|  
|P|proprietà: `Property` (incluse le proprietà predefinite)|  
|M|metodo: `Sub`, `Function`, `Declare`, `Operator`|  
|E|Evento: `Event`|  
|!|stringa di errore<br /><br /> Nella parte restante della stringa vengono fornite informazioni sull'errore. Il compilatore Visual Basic genera informazioni di errore per i collegamenti che non possono essere risolti.|  
  
-   La seconda parte di `String` è il nome completo dell'elemento, iniziando dalla radice dello spazio dei nomi. Il nome dell'elemento, i relativi tipi di inclusione e lo spazio dei nomi sono separati da punti. Se il nome dell'elemento stesso contiene punti, vengono sostituiti con il simbolo di cancelletto (#). Si presuppone che nessun elemento contiene un simbolo di cancelletto direttamente nel nome. Ad esempio, il nome completo del `String` costruttore sarebbe `System.String.#ctor`.  
  
-   Per le proprietà e i metodi, se il metodo ha degli argomenti, verrà incluso di seguito l'elenco degli argomenti racchiuso tra parentesi. Se non sono presenti argomenti, non verranno usate le parentesi. Gli argomenti sono separati da virgole. La codifica di ciascun argomento simile alla modalità di codifica un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] firma.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come le stringhe ID per una classe e i relativi membri vengono generati.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
