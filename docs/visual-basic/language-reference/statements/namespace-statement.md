---
title: Istruzione Namespace
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
ms.openlocfilehash: 0f1ba9a038fc604b6e4ede758891832e087fc096
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404434"
---
# <a name="namespace-statement"></a>Istruzione Namespace
Dichiara il nome di uno spazio dei nomi e fa in modo che il codice sorgente che segue la dichiarazione venga compilato in tale spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Parti  
 Globale  
 Facoltativa. Consente di definire uno spazio dei nomi all'esterno dello spazio dei nomi radice del progetto. Vedere [spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Obbligatorio. Nome univoco che identifica lo spazio dei nomi. Deve essere un identificatore di Visual Basic valido. Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Facoltativa. Elementi che costituiscono lo spazio dei nomi. Sono inclusi, tra gli altri, le enumerazioni, le strutture, le interfacce, le classi, i moduli, i delegati e altri spazi dei nomi.  
  
 `End Namespace`  
 Termina un `Namespace` blocco.  
  
## <a name="remarks"></a>Commenti  
 Gli spazi dei nomi vengono usati come sistema organizzativo. Forniscono un modo per classificare e presentare gli elementi di programmazione esposti ad altri programmi e applicazioni. Si noti che uno spazio dei nomi non è un *tipo* nel senso che una classe o una struttura è: non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di uno spazio dei nomi.  
  
 Tutti gli elementi di programmazione dichiarati dopo un' `Namespace` istruzione appartengono a tale spazio dei nomi. Visual Basic continua a compilare elementi nell'ultimo spazio dei nomi dichiarato fino a quando non rileva un' `End Namespace` istruzione o un'altra `Namespace` istruzione.  
  
 Se uno spazio dei nomi è già definito, anche all'esterno del progetto, è possibile aggiungervi elementi di programmazione. A tale scopo, è possibile utilizzare un' `Namespace` istruzione per indirizzare Visual Basic compilare elementi nello spazio dei nomi.  
  
 È possibile utilizzare un' `Namespace` istruzione solo a livello di file o di spazio dei nomi. Ciò significa che il *contesto di dichiarazione* per uno spazio dei nomi deve essere un file di origine o un altro spazio dei nomi e non può essere una classe, una struttura, un modulo, un'interfaccia o una routine. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
 È possibile dichiarare uno spazio dei nomi all'interno di un altro. Non esiste un limite limitato ai livelli di annidamento che è possibile dichiarare, ma tenere presente che quando altro codice accede agli elementi dichiarati nello spazio dei nomi più interno, deve usare una stringa di qualificazione contenente tutti i nomi degli spazi dei nomi nella gerarchia di nidificazione.  
  
## <a name="access-level"></a>Livello di accesso  
 Gli spazi dei nomi vengono considerati come se avessero un `Public` livello di accesso. È possibile accedere a uno spazio dei nomi dal codice in qualsiasi punto dello stesso progetto, da altri progetti che fanno riferimento al progetto e da qualsiasi assembly compilato dal progetto.  
  
 Gli elementi di programmazione dichiarati a livello di spazio dei nomi, ovvero in uno spazio dei nomi, ma non all'interno di altri elementi, possono avere `Public` o `Friend` accedere Se non è specificato, il livello di accesso di tale elemento usa `Friend` per impostazione predefinita. Gli elementi che è possibile dichiarare a livello di spazio dei nomi includono classi, strutture, moduli, interfacce, enumerazioni e delegati. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
## <a name="root-namespace"></a>Spazio dei nomi radice  
 Tutti i nomi degli spazi dei nomi nel progetto sono basati su uno *spazio dei nomi radice*. Visual Studio assegna il nome del progetto come spazio dei nomi radice predefinito per tutto il codice del progetto. Se, ad esempio, il progetto è denominato `Payroll`, i relativi elementi di programmazione appartengono allo spazio dei nomi `Payroll`. Se si dichiara `Namespace funding` , il nome completo dello spazio dei nomi è `Payroll.funding` .  
  
 Se si desidera specificare uno spazio dei nomi esistente in un' `Namespace` istruzione, ad esempio nell'esempio della classe di elenco generico, è possibile impostare lo spazio dei nomi radice su un valore null. A tale scopo, fare clic su **Proprietà progetto** dal menu **progetto** , quindi deselezionare la voce **spazio dei nomi radice** in modo che la casella sia vuota. Se questa operazione non è stata eseguita nell'esempio di classe di elenco generico, il compilatore Visual Basic accetta `System.Collections.Generic` come nuovo spazio dei nomi all'interno del progetto `Payroll` , con il nome completo di `Payroll.System.Collections.Generic` .  
  
 In alternativa, è possibile usare la `Global` parola chiave per fare riferimento a elementi di spazi dei nomi definiti all'esterno del progetto. Questa operazione consente di mantenere il nome del progetto come spazio dei nomi radice. In questo modo si riduce la possibilità di unire involontariamente gli elementi di programmazione insieme a quelli degli spazi dei nomi esistenti. Per ulteriori informazioni, vedere la sezione "parola chiave Global in nomi completi" in [spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 La `Global` parola chiave può essere utilizzata anche in un'istruzione dello spazio dei nomi. Ciò consente di definire uno spazio dei nomi all'esterno dello spazio dei nomi radice del progetto. Per ulteriori informazioni, vedere la sezione "parola chiave Global nelle istruzioni dello spazio dei nomi" negli [spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 **Risoluzione dei problemi.** Lo spazio dei nomi radice può causare concatenazioni impreviste dei nomi degli spazi dei nomi. Se si fa riferimento agli spazi dei nomi definiti all'esterno del progetto, il compilatore Visual Basic può interpretarerli come spazi dei nomi annidati nello spazio dei nomi radice. In tal caso, il compilatore non riconosce alcun tipo già definito negli spazi dei nomi esterni. Per evitare questo problema, impostare lo spazio dei nomi radice su un valore null come descritto in "spazio dei nomi radice" oppure utilizzare la `Global` parola chiave per accedere agli elementi degli spazi dei nomi esterni.  
  
## <a name="attributes-and-modifiers"></a>Attributi e modificatori  
 Non è possibile applicare attributi a uno spazio dei nomi. Un attributo fornisce informazioni ai metadati dell'assembly, che non sono significativi per i classificatori di origine, ad esempio gli spazi dei nomi.  
  
 In uno spazio dei nomi non è possibile applicare alcun modificatore di accesso o di routine o altri modificatori. Poiché non è un tipo, questi modificatori non sono significativi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono dichiarati due spazi dei nomi, uno annidato nell'altro.  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono dichiarati più spazi dei nomi annidati su una sola riga ed è equivalente all'esempio precedente.  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene accesso alla classe definita negli esempi precedenti.  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definita la struttura di una nuova classe di elenco generica che viene aggiunta allo <xref:System.Collections.Generic?displayProperty=nameWithType> spazio dei nomi.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Imports (tipo e spazio dei nomi .NET)](imports-statement-net-namespace-and-type.md)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
