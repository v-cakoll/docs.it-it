---
title: Elaborazione del file XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: a10255be140c7c86a435cca98cec5df7df82ffee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842096"
---
# <a name="processing-the-xml-file-visual-basic"></a>Elaborazione del file XML (Visual Basic)
Il compilatore genera una stringa identificativa (ID) per ciascun costrutto del codice che contiene tag per la creazione della documentazione. (Per informazioni su come contrassegnare il codice, vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md).) La stringa ID identifica in modo univoco il costrutto. I programmi che elaborano il file XML è possono usare la stringa ID per identificare il corrispondente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] elemento metadati/reflection.  
  
 Il file XML non è una rappresentazione gerarchica del codice. è un elenco semplice con un ID generato per ogni elemento.  
  
 Per generare gli ID, il compilatore applica le regole seguenti:  
  
-   Assenza di spazi vuoti nella stringa.  
  
-   La prima parte della stringa ID specifica il tipo di membro, con un singolo carattere seguito dai due punti. Vengono usati i seguenti tipi di membro.  
  
|Carattere|Descrizione|  
|---|---|  
|N|namespace<br /><br /> È possibile aggiungere i commenti della documentazione a uno spazio dei nomi, ma è possibile creare riferimenti CREF a loro, in cui è supportata.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|campo: `Dim`|  
|P|proprietà: `Property` (incluse le proprietà di impostazione predefinita)|  
|M|metodo: `Sub`, `Function`, `Declare`, `Operator`|  
|E|evento: `Event`|  
|!|stringa di errore<br /><br /> Nella parte restante della stringa vengono fornite informazioni sull'errore. Il compilatore Visual Basic genera informazioni di errore per i collegamenti che non possono essere risolto.|  
  
-   La seconda parte di `String` è il nome completo dell'elemento, iniziando dalla radice dello spazio dei nomi. Il nome dell'elemento, relativo i tipi di inclusione e lo spazio dei nomi sono separati da punti. Se il nome dell'elemento stesso contiene punti, vengono sostituiti con il simbolo di cancelletto (#). Si presuppone che nessun elemento contiene un simbolo di cancelletto direttamente nel nome. Ad esempio, il nome completo del `String` costruttore sarebbe `System.String.#ctor`.  
  
-   Per le proprietà e i metodi, se il metodo ha degli argomenti, verrà incluso di seguito l'elenco degli argomenti racchiuso tra parentesi. Se non sono presenti argomenti, non verranno usate le parentesi. Gli argomenti sono separati da virgole. La codifica di ciascun argomento simile alla modalità di codifica un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] firma.  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra come le stringhe di ID per una classe e i relativi membri vengono generati.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
