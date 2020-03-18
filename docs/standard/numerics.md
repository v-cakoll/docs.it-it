---
title: Valori numerici in .NET
ms.date: 10/18/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
ms.openlocfilehash: e5815058898cac165e7a47d761ee86bb9c4cb940
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091596"
---
# <a name="numerics-in-net"></a>Valori numerici in .NET

.NET supporta una gamma di primitive intere e a virgola mobile numeriche, nonché <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, un tipo integrale senza limite teorico superiore o inferiore, <xref:System.Numerics.Complex?displayProperty=nameWithType>, che rappresenta numeri complessi, e un set di tipi abilitati per SIMD nello spazio dei nomi <xref:System.Numerics>.
  
## <a name="integer-types"></a>Tipi integer

.NET supporta tipi integer a 8, 16, 32 e 64 bit con o senza segno, elencati nella tabella seguente:
  
|Type|Con segno/Senza segno|Dimensioni (in byte)|Valore minimo|Valore massimo|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|Senza segno|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|Firmato|2|-32,768|32.767|  
|<xref:System.Int32?displayProperty=nameWithType>|Firmato|4|-2,147,483,648|2.147.483.647|  
|<xref:System.Int64?displayProperty=nameWithType>|Firmato|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=nameWithType>|Firmato|1|-128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|Senza segno|2|0|65.535|  
|<xref:System.UInt32?displayProperty=nameWithType>|Senza segno|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=nameWithType>|Senza segno|8|0|18,446,744,073,709,551,615|  
  
Ogni tipo integer supporta un set di operatori aritmetici standard. La classe <xref:System.Math?displayProperty=nameWithType> fornisce metodi per un set più ampio di funzioni matematiche.

È anche possibile operare sui singoli bit di un valore Integer usando la <xref:System.BitConverter?displayProperty=nameWithType> classe.  

> [!NOTE]  
> I tipi integer senza segno non sono conformi a CLS. Per altre informazioni, vedere [Language Independence and Language-Independent Components](language-independence-and-language-independent-components.md).

## <a name="biginteger"></a>BigInteger

La struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> è un tipo immutabile che rappresenta un integer arbitrariamente grande il cui valore in teoria non ha limiti inferiori o superiori. I metodi del tipo <xref:System.Numerics.BigInteger> sono strettamente paralleli a quelli di altri tipi integrali.
  
## <a name="floating-point-types"></a>Tipi a virgola mobile

.NET include tre tipi primitivi a virgola mobile, elencati nella tabella seguente:
  
|Type|Dimensioni (in byte)|Intervallo approssimativo|Precision|  
|----------|--------|---------------------|--------------------|  
|<xref:System.Single?displayProperty=nameWithType>|4|Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup>|~6-9 cifre|  
|<xref:System.Double?displayProperty=nameWithType>|8|Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup>|~15-17 cifre|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup>|28-29 cifre|  
  
I tipi <xref:System.Single> e <xref:System.Double> supportano entrambi valori speciali che rappresentano un valore non numerico e infinito. Ad esempio, il tipo <xref:System.Double> fornisce questi valori: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>. Per testare questi valori speciali, è necessario usare i metodi <xref:System.Double.IsNaN%2A?displayProperty=nameWithType>, <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType>, <xref:System.Double.IsPositiveInfinity%2A?displayProperty=nameWithType> e <xref:System.Double.IsNegativeInfinity%2A?displayProperty=nameWithType>.

Ogni tipo a virgola mobile supporta un set di operatori aritmetici standard. La classe <xref:System.Math?displayProperty=nameWithType> fornisce metodi per un set più ampio di funzioni matematiche. .NET core 2.0 e versioni successive include la classe <xref:System.MathF?displayProperty=nameWithType>, che fornisce metodi che accettano argomenti del tipo <xref:System.Single>.

È anche possibile operare sui singoli bit dei valori <xref:System.Double> e <xref:System.Single> usando la classe <xref:System.BitConverter?displayProperty=nameWithType>. La struttura <xref:System.Decimal?displayProperty=nameWithType> dispone di metodi specifici, <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> e <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=nameWithType>, che consentono di operare sui singoli bit di un valore decimale, nonché di un set di metodi specifici per l'esecuzione di altre operazioni matematiche.
  
I tipi <xref:System.Double> e <xref:System.Single> sono destinati a essere usati per valori imprecisi per natura, ad esempio la distanza tra due stelle, e per applicazioni in cui non è necessario un livello elevato di precisione e gli errori di arrotondamento non devono essere minimi. Per i casi in cui è necessaria una maggiore precisione e gli errori di arrotondamento devono essere minimi, è consigliabile usare il tipo <xref:System.Decimal?displayProperty=nameWithType>.

> [!NOTE]
> Il tipo <xref:System.Decimal> non elimina la necessità di arrotondamento. Piuttosto, riduce al minimo gli errori dovuti all'arrotondamento.
  
## <a name="complex"></a>Complex

La struttura <xref:System.Numerics.Complex?displayProperty=nameWithType> rappresenta un numero complesso, ovvero un numero costituito da una parte numerica reale e una parte numerica immaginaria. Supporta un set standard di operatori aritmetici, di confronto, di uguaglianza, di conversione esplicita e di conversione implicita, oltre che metodi matematici, algebrici e trigonometrici.  
  
## <a name="simd-enabled-types"></a>Tipi abilitati per SIMD

Lo spazio dei nomi <xref:System.Numerics> include un set di tipi .NET abilitati per SIMD. Operazioni SIMD (Single Instruction Multiple Data) possono essere eseguite in parallelo a livello hardware. Questo approccio aumenta la velocità effettiva dei calcoli vettorializzati, che sono comuni in app matematiche scientifiche e grafiche.
  
Tra i tipi .NET abilitati per SIMD sono inclusi i seguenti:

- Tipi <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> e <xref:System.Numerics.Vector4>, che rappresentano i vettori con 2, 3 e 4 valori <xref:System.Single>.

- Due tipi matrice: <xref:System.Numerics.Matrix3x2>, che rappresenta una matrice 3x2, e <xref:System.Numerics.Matrix4x4>, che rappresenta una matrice 4x4.

- Tipo <xref:System.Numerics.Plane>, che rappresenta un piano nello spazio tridimensionale.

- Tipo <xref:System.Numerics.Quaternion>, che rappresenta un vettore usato per codificare le rotazioni fisiche tridimensionali.

- Tipo <xref:System.Numerics.Vector%601>, che rappresenta un vettore di un tipo numerico specificato e fornisce un ampio set di operatori che traggono vantaggio dal supporto per SIMD. Il conteggio di un'istanza <xref:System.Numerics.Vector%601> è fisso, ma il suo valore <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> dipende dalla CPU del computer, in cui viene eseguito codice.
  > [!NOTE]
  > Il tipo <xref:System.Numerics.Vector%601> non è incluso in .NET Framework. È necessario installare il pacchetto NuGet [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) per ottenere l'accesso a questo tipo.
  
I tipi abilitati per SIMD vengono implementati in modo da poter essere usati con hardware non abilitato per SIMD in compilatori JIT. Per poter trarre vantaggio dalle istruzioni SIMD, le app a 64 bit devono essere eseguite dal runtime che usa il compilatore RyuJIT, che è incluso in .NET Core e in .NET Framework 4.6 e versioni successive. Aggiunge il supporto per SIMD quando i processori di destinazione sono a 64 bit.

## <a name="see-also"></a>Vedere anche

- [Concetti di base sulle applicazioni](application-essentials.md)
- [Stringhe di formato numerico standard](base-types/standard-numeric-format-strings.md)
