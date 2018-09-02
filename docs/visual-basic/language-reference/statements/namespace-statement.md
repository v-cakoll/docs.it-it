---
title: Istruzione Namespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 28016763b2cef2e8b8954f486bbbdb6930b5364c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417412"
---
# <a name="namespace-statement"></a>Istruzione Namespace
Dichiara il nome di uno spazio dei nomi e fa sì che il codice sorgente che segue la dichiarazione deve essere compilato all'interno di tale spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Parti  
 Global  
 Facoltativo. Consente di definire uno spazio dei nomi all'esterno di spazio dei nomi radice del progetto. Visualizzare [spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Obbligatorio. Un nome univoco che identifica lo spazio dei nomi. Deve essere un valido identificatore Visual Basic. Per altre informazioni, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Facoltativo. Elementi che costituiscono lo spazio dei nomi. Queste includono, ma non sono limitate a, enumerazioni, strutture, interfacce, classi, moduli, i delegati e altri spazi dei nomi.  
  
 `End Namespace`  
 Termina un `Namespace` blocco.  
  
## <a name="remarks"></a>Note  
 Gli spazi dei nomi vengono usati come un sistema azienda. Forniscono un modo per classificare e presentare gli elementi di programmazione che vengono esposte ad altre applicazioni e programmi. Si noti che uno spazio dei nomi non è un *tipo* nel senso che è una classe o struttura, ovvero non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di uno spazio dei nomi.  
  
 Tutti gli elementi di programmazione dichiarati dopo un `Namespace` istruzione appartengono allo spazio dei nomi. Visual Basic continua a compilare elementi nello spazio dei nomi dichiarato ultimo fino a quando non viene rilevata un' `End Namespace` istruzione o un altro `Namespace` istruzione.  
  
 Se uno spazio dei nomi è già definito, anche all'esterno del progetto, è possibile aggiungere elementi di programmazione a esso. A tale scopo, si utilizza un `Namespace` istruzione per indirizzare Visual Basic per compilare elementi in tale spazio dei nomi.  
  
 È possibile usare un `Namespace` istruzione solo a livello di file o spazio dei nomi. Ciò significa che il *contesto della dichiarazione* per uno spazio dei nomi deve essere un file di origine o un altro spazio dei nomi e non può essere una classe, struttura, modulo, interfaccia o procedure. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 È possibile dichiarare uno spazio dei nomi all'interno di altra. Non sono previsti limiti rigidi per i livelli di annidamento è possibile dichiarare, ma tenere presente che quando l'altro codice accede agli elementi dichiarati nello spazio dei nomi di colonne più interno, deve usare una stringa di qualificazione che contiene tutti i nomi dello spazio dei nomi nella gerarchia di annidamento.  
  
## <a name="access-level"></a>Livello di accesso  
 Gli spazi dei nomi vengono trattati come se fosse un `Public` livello di accesso. Uno spazio dei nomi sono accessibili dal codice in qualsiasi punto nello stesso progetto, da altri progetti che fanno riferimento al progetto e da qualsiasi assembly compilato dal progetto.  
  
 Gli elementi di programmazione dichiarati a livello di spazio dei nomi, vale a dire in uno spazio dei nomi ma non all'interno di qualsiasi altro elemento, possono avere `Public` o `Friend` accesso. Se non viene specificato, il livello di accesso di ad esempio un elemento Usa `Friend` per impostazione predefinita. Gli elementi che è possibile dichiarare a livello di spazio dei nomi includono classi, strutture, moduli, interfacce, enumerazioni e delegati. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## <a name="root-namespace"></a>Namespace radice  
 Tutti i nomi dello spazio dei nomi nel progetto si basano su un *spazio dei nomi radice*. Visual Studio assegna il nome del progetto come spazio dei nomi radice predefinito per tutto il codice del progetto. Se, ad esempio, il progetto è denominato `Payroll`, i relativi elementi di programmazione appartengono allo spazio dei nomi `Payroll`. Se si dichiara `Namespace funding`, il nome completo dello spazio dei nomi è `Payroll.funding`.  
  
 Se si desidera specificare uno spazio dei nomi esistente in un `Namespace` istruzione, come nell'esempio della classe di elenco generico, è possibile impostare lo spazio dei nomi radice per un valore null. A tale scopo, fare clic su **le proprietà del progetto** dal **Project** menu e quindi deselezionare la **dello spazio dei nomi radice** voce in modo che la casella è vuota. Se non è stato questo nell'esempio di classe di elenco generico, il compilatore Visual Basic richiederebbe `System.Collections.Generic` come un nuovo spazio dei nomi all'interno di progetto `Payroll`, con il nome completo del `Payroll.System.Collections.Generic`.  
  
 In alternativa, è possibile usare il `Global` una parola chiave per fare riferimento agli elementi degli spazi dei nomi definiti all'esterno del progetto. Questa operazione consente di mantenere il nome del progetto come spazio dei nomi radice. In questo modo si riduce la possibilità di involontariamente unire gli elementi di programmazione insieme a quelle degli spazi dei nomi esistente. Per altre informazioni, vedere la sezione "Global (parola chiave) in nomi completi" nella [spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 Il `Global` parola chiave può essere utilizzata anche in un'istruzione Namespace. Ciò consente di definire uno spazio dei nomi all'esterno dello spazio dei nomi radice del progetto. Per altre informazioni, vedere la sezione "Parola chiave Global in istruzioni Namespace" nella [spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **Risoluzione dei problemi.** Lo spazio dei nomi radice può causare impreviste concatenazioni di spazi dei nomi. Se si fa riferimento a spazi dei nomi definiti all'esterno del progetto, il compilatore Visual Basic può interpretarli come gli spazi dei nomi annidato nello spazio dei nomi radice. In tal caso, il compilatore non riconosce eventuali tipi che sono stati già definiti negli spazi dei nomi esterno. Per evitare questo problema, impostare lo spazio dei nomi radice per un valore null come descritto nella "Radice Namespace" oppure usare il `Global` parola chiave per accedere agli elementi degli spazi dei nomi esterno.  
  
## <a name="attributes-and-modifiers"></a>Attributi e i modificatori  
 È possibile applicare attributi per uno spazio dei nomi. Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativa per classificatori di origine, ad esempio gli spazi dei nomi.  
  
 È possibile applicare tutti gli accessi o modificatori di procedure o altri modificatori, uno spazio dei nomi. Perché non è un tipo, questi modificatori non sono significativi.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara due spazi dei nomi, uno annidato in altro.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara più spazi dei nomi annidati in una singola riga ed è equivalente all'esempio precedente.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accede la classe definita negli esempi precedenti.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente definisce la struttura di una nuova classe di elenco generico e lo aggiunge al <xref:System.Collections.Generic?displayProperty=nameWithType> dello spazio dei nomi.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
