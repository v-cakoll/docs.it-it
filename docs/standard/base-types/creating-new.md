---
title: Creazione di nuove stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: ef65c50111d6ba91ab70d0b9c8cb90c606f9366c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73103822"
---
# <a name="creating-new-strings-in-net"></a>Creazione di nuove stringhe in .NET
.NET Framework consente di creare stringhe usando una semplice assegnazione, oltre a eseguire l'overload del costruttore di classe per supportare la creazione di stringhe tramite una serie di parametri diversi. .NET Framework offre anche diversi metodi nella classe <xref:System.String?displayProperty=nameWithType> per creare nuovi oggetti stringa combinando più stringhe, matrici di stringhe o oggetti.  
  
## <a name="creating-strings-using-assignment"></a>Creazione di stringhe tramite assegnazione  
 Il modo più semplice per creare un nuovo oggetto <xref:System.String> consiste nell'assegnare un valore letterale stringa a un oggetto <xref:System.String>.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Creazione di stringhe tramite un costruttore di classe  
 È possibile usare overload del costruttore della classe <xref:System.String> per creare stringhe da matrici di caratteri. È anche possibile creare una nuova stringa duplicando un determinato carattere per un numero specifico di volte.  
  
## <a name="methods-that-return-strings"></a>Metodi che restituiscono stringhe  
 Nella tabella seguente sono elencati diversi metodi utili che restituiscono nuovi oggetti stringa.  
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|Compila una stringa formattata da un insieme di oggetti di input.|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|Compila stringhe da due o più stringhe.|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|Compila una nuova stringa combinando una matrice di stringhe.|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|Compila una nuova stringa inserendo una stringa in corrispondenza dell'indice specificato di una stringa esistente.|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|Copia i caratteri specificati di una stringa in una determinata posizione all'interno di una matrice di caratteri.|  
  
### <a name="format"></a>Format  
 È possibile usare il metodo **String.Format** per creare stringhe formattate e concatenare stringhe che rappresentano più oggetti. Qualsiasi oggetto venga passato a questo metodo viene automaticamente convertito in una stringa. Se ad esempio l'applicazione deve visualizzare un valore **Int32** e un valore **DateTime**, è possibile costruire con facilità una stringa che rappresenti tali valori usando il metodo **Format**. Per altre informazioni sulle convenzioni di formattazione usate con questo metodo, vedere la sezione relativa alla [formattazione composita](../../../docs/standard/base-types/composite-formatting.md).  
  
 L'esempio di codice seguente usa il metodo **Format** per creare una stringa che usa una variabile integer.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 In questo esempio <xref:System.DateTime.Now%2A?displayProperty=nameWithType> visualizza l'ora e la data correnti nel modo specificato dalle impostazioni cultura associate al thread corrente.  
  
### <a name="concat"></a>Concat  
 Il metodo **String.Concat** può essere usato per creare facilmente un nuovo oggetto stringa da due o più oggetti esistenti. Questo metodo rappresenta una modalità di concatenamento delle stringhe indipendente dal linguaggio. Il metodo accetta qualsiasi classe derivi da **System.Object**. Nell'esempio di codice che segue viene creata una stringa da due oggetti stringa esistenti e da un carattere di separazione.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 Il metodo **String.Join** consente di creare una nuova stringa da una matrice di stringhe e da una stringa di separazione. Questo metodo è utile per concatenare più stringhe, creando un elenco, eventualmente separato da virgole.  
  
 Nell'esempio di codice seguente viene usato uno spazio per eseguire l'associazione di una matrice di stringhe.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 Il metodo **String.Insert** consente di creare una nuova stringa inserendo una stringa in una posizione specificata in un'altra stringa. Questo metodo usa un indice a base zero. Nell'esempio di codice che segue viene inserita una stringa in corrispondenza della quinta posizione di indice di `MyString` e viene creata una nuova stringa con tale valore.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 Il metodo **String.CopyTo** consente di copiare parti di una stringa in una matrice di caratteri. È possibile specificare sia l'indice iniziale della stringa sia il numero dei caratteri da copiare. Il metodo contiene l'indice di origine, una matrice di caratteri, l'indice di destinazione e il numero dei caratteri da copiare. Tutti gli indici sono a base zero.  
  
 Nell'esempio di codice riportato di seguito il metodo **CopyTo** viene usato per copiare nella prima posizione di indice di una matrice di caratteri i caratteri della parola "Hello" di un oggetto stringa.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Operazioni di base sulle stringheBasic String Operations](../../../docs/standard/base-types/basic-string-operations.md)
- [Formattazione composita](../../../docs/standard/base-types/composite-formatting.md)
