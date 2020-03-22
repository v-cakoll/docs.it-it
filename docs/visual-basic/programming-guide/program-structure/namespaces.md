---
title: Spazi dei nomi
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: ec892167f30a7ded739dc188ab4096cb3a5d154c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400673"
---
# <a name="namespaces-in-visual-basic"></a>Spazi dei nomi in Visual Basic
Gli spazi dei nomi organizzano gli oggetti definiti in un assembly. Gli assembly possono contenere più spazi dei nomi, che a loro volta possono contenere altri spazi dei nomi. Gli spazi dei nomi consentono di evitare problemi di ambiguità e di semplificare i riferimenti quando si usano gruppi di oggetti di grandi dimensioni, ad esempio librerie di classi.  
  
 Ad esempio, .NET Framework <xref:System.Windows.Forms.ListBox> definisce <xref:System.Windows.Forms?displayProperty=nameWithType> la classe nello spazio dei nomi . Il frammento di codice seguente illustra come dichiarare una variabile usando il nome completo per questa classe:  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a>Evitare conflitti di nomi  
 Gli spazi dei nomi .NET Framework risolvono un problema talvolta denominato *inquinamento dello spazio dei nomi*, in cui lo sviluppatore di una libreria di classi è ostacolato dall'uso di nomi simili in un'altra libreria. Questi conflitti con i componenti esistenti sono talvolta denominati *conflitti di nomi*.  
  
 Se, ad esempio, si crea una nuova classe denominata `ListBox`, è possibile usarla all'interno del progetto senza qualificazione. Tuttavia, se si desidera utilizzare <xref:System.Windows.Forms.ListBox> la classe .NET Framework nello stesso progetto, è necessario utilizzare un riferimento completo per rendere univoco il riferimento. Se il riferimento non è univoco, Visual Basic genera un errore che indica che il nome è ambiguo. L'esempio di codice seguente illustra come dichiarare questi oggetti:  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 Nella figura seguente vengono illustrate due gerarchie di spazi dei nomi, entrambe contenenti un oggetto denominato `ListBox`:  
  
 ![Screenshot che mostra due gerarchie di spazi dei nomi.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 Per impostazione predefinita, ogni file eseguibile creato con Visual Basic contiene uno spazio dei nomi con lo stesso nome del progetto. Se, ad esempio, si definisce un oggetto all'interno di un progetto denominato `ListBoxProject`, il file eseguibile ListBoxProject.exe conterrà uno spazio dei nomi chiamato `ListBoxProject`.  
  
 Più assembly possono usare lo stesso spazio dei nomi. Visual Basic li considera come un singolo set di nomi. È ad esempio possibile definire classi per uno spazio dei nomi chiamato `SomeNameSpace` in un assembly denominato `Assemb1`e altre classi per lo stesso spazio dei nomi da un assembly denominato `Assemb2`.  
  
## <a name="fully-qualified-names"></a>nomi completi  
 I nomi completi sono riferimenti a oggetti preceduti dal nome dello spazio dei nomi in cui è definito l'oggetto. È possibile usare gli oggetti definiti in altri progetti se si crea un riferimento alla classe (scegliendo **Aggiungi riferimento** dal menu **Progetto** ) e quindi usare il nome completo per l'oggetto nel codice. Il frammento di codice seguente mostra come usare il nome completo per un oggetto dallo spazio dei nomi di un altro progetto:  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 I nomi completi impediscono i conflitti di denominazione perché consentono al compilatore di determinare quale oggetto viene usato. I nomi stessi, tuttavia, possono diventare lunghi e complessi. Per evitare questo problema, è possibile usare l'istruzione `Imports` per definire un *alias*, ossia un nome abbreviato utilizzabile al posto di un nome completo. Ad esempio, il codice seguente crea alias per due nomi completi e usa questi alias per definire due oggetti.  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 Se si usa l'istruzione `Imports` senza un alias, è possibile usare tutti i nomi dello spazio dei nomi senza qualificazione, a condizione che siano univoci per il progetto. Se il progetto contiene istruzioni `Imports` per gli spazi dei nomi che contengono elementi con lo stesso nome, quando si usa il nome è necessario definirlo in modo completo. Si supponga, ad esempio, che il progetto contenga le due istruzioni `Imports` seguenti:  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 Se si tenta `Class1` di utilizzare senza qualificarlo completamente, Visual `Class1` Basic genera un errore che indica che il nome è ambiguo.  
  
## <a name="namespace-level-statements"></a>Istruzioni a livello di spazio dei nomi  
 All'interno di uno spazio dei nomi è possibile definire elementi quali moduli, interfacce, classi, delegati, enumerazioni, strutture e altri spazi dei nomi. Non è invece possibile definire elementi come proprietà, routine, variabili ed eventi a livello di spazio dei nomi. Questi elementi devono essere dichiarati all'interno di contenitori quali moduli, strutture o classi.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Parola chiave Global nei nomi completi  
 Se è stata definita una gerarchia annidata di spazi dei nomi, è possibile che per il codice interno alla gerarchia venga bloccato l'accesso allo spazio dei nomi <xref:System?displayProperty=nameWithType> di .NET Framework. L'esempio seguente illustra una gerarchia in cui lo spazio dei nomi `SpecialSpace.System` blocca l'accesso a <xref:System?displayProperty=nameWithType>.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Di conseguenza, il compilatore di Visual Basic non è in grado di risolvere il riferimento a <xref:System.Int32?displayProperty=nameWithType>perché `SpecialSpace.System` non definisce `Int32`. Per iniziare la catena di qualificazione al livello più esterno della libreria di classi di .NET Framework è possibile usare la parola chiave `Global` . In questo modo si può specificare lo spazio dei nomi <xref:System?displayProperty=nameWithType> o qualsiasi altro spazio dei nomi nella libreria di classi. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Usando `Global` è possibile accedere ad altri spazi dei nomi a livello di radice, ad esempio <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, e a qualsiasi spazio dei nomi associato al progetto.  
  
## <a name="global-keyword-in-namespace-statements"></a>Parola chiave Global nelle istruzioni degli spazi dei nomi  
 La parola chiave `Global` può essere usata anche in un oggetto [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md). Ciò consente di definire uno spazio dei nomi all'esterno dello spazio dei nomi radice del progetto.  
  
 Tutti gli spazi dei nomi inclusi nel progetto sono basati sullo spazio dei nomi radice definito per il progetto.  Visual Studio assegna il nome del progetto come spazio dei nomi radice predefinito per tutto il codice del progetto. Se, ad esempio, il progetto è denominato `ConsoleApplication1`, i relativi elementi di programmazione appartengono allo spazio dei nomi `ConsoleApplication1`. Se si dichiara `Namespace Magnetosphere`, i riferimenti a `Magnetosphere` nel progetto accedono a `ConsoleApplication1.Magnetosphere`.  
  
 Negli esempi seguenti viene usata la parola chiave `Global` per dichiarare uno spazio dei nomi all'esterno dello spazio dei nomi radice per il progetto.  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 In una dichiarazione dello spazio dei nomi la parola chiave `Global` non può essere annidata in un altro spazio dei nomi.  
  
 È possibile usare [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) per visualizzare e modificare lo **spazio dei nomi radice** del progetto.  Per i nuovi progetti, come **spazio dei nomi radice** predefinito viene usato il nome del progetto. Per impostare `Global` come spazio dei nomi di primo livello, è possibile cancellare la voce **Spazio dei nomi radice** in modo da lasciare vuota la casella. La cancellazione della voce **Spazio dei nomi radice** elimina la necessità di usare la parola chiave `Global` nelle dichiarazioni degli spazi dei nomi.  
  
 Se un'istruzione `Namespace` dichiara un nome che è anche uno spazio dei nomi in .NET Framework e la parola chiave `Global` non viene usata in un nome completo, lo spazio dei nomi di .NET Framework non sarà più disponibile. Per abilitare l'accesso allo spazio dei nomi di .NET Framework senza usare la parola chiave `Global` , è possibile includere `Global` nell'istruzione `Namespace` .  
  
 L'esempio seguente mostra la dichiarazione dello spazio dei nomi `Global` con la parola chiave `System.Text` .  
  
 Se `Global` non è presente nella dichiarazione dello spazio dei nomi, <xref:System.Text.StringBuilder> non è accessibile, a meno che non si specifichi `Global.System.Text.StringBuilder`. Per un progetto denominato `ConsoleApplication1`, i riferimenti a `System.Text` accedono a `ConsoleApplication1.System.Text` se non viene usata la parola chiave `Global` .  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Riferimenti e istruzione Imports](references-and-the-imports-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Scrittura di codice nelle soluzioni Office](/visualstudio/vsto/writing-code-in-office-solutions)
