---
title: Accesso ad attributi personalizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 393fb3516756438325c9f3fd00941b963b3f2a2e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-custom-attributes"></a>Accesso ad attributi personalizzati
Dopo che gli attributi sono stati associati a elementi del programma, è possibile verificarne l'esistenza ed esaminarne i valori tramite reflection. In .NET Framework versioni 1.0 e 1.1 gli attributi personalizzati vengono esaminati nel contesto di esecuzione. .NET Framework versione 2.0 offre un nuovo contesto di caricamento di sola reflection, che consente di esaminare il codice che non può essere caricato per l'esecuzione.  
  
## <a name="the-reflection-only-context"></a>Contesto di sola reflection  
 Il codice caricato nel contesto di sola reflection non può essere eseguito. Non è pertanto possibile creare istanze di attributi personalizzati, operazione per cui è richiesta l'esecuzione dei costruttori. Per caricare ed esaminare gli attributi personalizzati nel contesto di sola reflection, usare la classe <xref:System.Reflection.CustomAttributeData>. È possibile ottenere istanze di questa classe usando l'overload appropriato del metodo <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> statico. Vedere [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Procedura: Caricare assembly nel contesto di sola reflection).  
  
## <a name="the-execution-context"></a>Contesto di esecuzione  
 I principali metodi di reflection per l'esecuzione di query sugli attributi nel contesto di esecuzione sono <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> e <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>.  
  
 L'accessibilità di un attributo personalizzato viene controllata in riferimento all'assembly a cui l'attributo è collegato. In altri termini, si verifica se un metodo di un tipo dell'assembly a cui è collegato l'attributo personalizzato può chiamare il costruttore dell'attributo personalizzato.  
  
 I metodi come <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> consentono di controllare la visibilità e l'accessibilità dell'argomento di tipo. È possibile recuperare un attributo personalizzato del tipo definito dall'utente tramite **GetCustomAttributes** solo nel codice dell'assembly che contiene tale tipo.  
  
 Nell'esempio in C# riportato di seguito viene rappresentato un tipico modello di progettazione di attributi personalizzati. Viene illustrato il modello di reflection degli attributi personalizzati adottato dal runtime.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 Se il runtime tenta di recuperare gli attributi personalizzati del tipo di attributo personalizzato pubblico <xref:System.ComponentModel.DescriptionAttribute> associato al metodo **GetLanguage**, esegue le azioni seguenti:  
  
1.  Controlla che l'argomento di tipo **DescriptionAttribute** a **Type.GetCustomAttributes**(Tipo *tipo*) sia pubblico e quindi visibile e accessibile.  
  
2.  Controlla che il tipo definito dall'utente **MyDescriptionAttribute** che deriva da **DescriptionAttribute** sia visibile e accessibile all'interno dell'assembly **System.Web.DLL**, in cui è collegato al metodo **GetLanguage**().  
  
3.  Controlla che il costruttore di **MyDescriptionAttribute** sia visibile e accessibile all'interno dell'assembly **System.Web.DLL**.  
  
4.  Chiama il costruttore di **MyDescriptionAttribute** con i parametri dell'attributo personalizzato e restituisce il nuovo oggetto al chiamante.  
  
 Il modello di reflection degli attributi personalizzati può perdere istanze di tipi definiti dall'utente all'esterno dell'assembly in cui il tipo è definito. Questo modello non differisce da quello in cui si inquadrano i membri della libreria di sistema del runtime, che restituiscono istanze di tipi definiti dall'utente, come <xref:System.Type.GetMethods%2A?displayProperty=fullName> che restituisce una matrice di oggetti **RuntimeMethodInfo**. Per impedire a un client di rilevare informazioni su un attributo personalizzato definito dall'utente, definire i membri del tipo come non pubblici.  
  
 Nell'esempio seguente viene illustrato il metodo principale per accedere agli attributi personalizzati tramite reflection.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)] [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)] [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)  (Visualizzazione delle informazioni sul tipo)  
 [Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md) (Considerazioni sulla sicurezza per reflection)

