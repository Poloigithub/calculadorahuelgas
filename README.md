# Calculadora del Coste de la Huelga

Calculadora web que estima el coste económico neto para el trabajador de participar en una huelga y el tiempo necesario para recuperar esa inversión con el aumento salarial conseguido.

Disponible en: **https://poloigithub.github.io/calculadorahuelgas/**

---

## Campos de entrada

| Campo | Descripción |
|---|---|
| Salario bruto mensual | Salario mensual antes de impuestos y cotizaciones |
| Pagas extra anuales | Importe total de pagas extraordinarias al año |
| Tipo marginal IRPF | Tramo del IRPF que aplica al trabajador (0 %–47 %) |
| Días de huelga | Número de días que se secundará la huelga |
| Aumento mensual neto esperado | Mejora salarial neta mensual que se espera conseguir |

---

## Fórmulas aplicadas

### 1. Coste bruto por día de huelga

```
Coste bruto/día = [(Salario bruto mensual ÷ 30) + (Pagas extra anuales ÷ 365)] × 1,4
```

El factor **1,4** (= 7 ÷ 5) recoge el descuento proporcional del descanso semanal: por cada 5 días laborables en huelga, la empresa también descuenta el día de descanso semanal que les corresponde.

### 2. Descuentos del trabajador — Seguridad Social (fijo)

Por los días de huelga el trabajador no cotiza, lo que reduce el coste real:

| Concepto | Tipo |
|---|---|
| Contingencias comunes | 4,70 % |
| Desempleo | 1,65 % |
| Formación profesional | 0,15 % |
| **Total SS obrera** | **6,50 %** |

### 3. Descuento IRPF

El salario no percibido tampoco tributa, por lo que el trabajador se ahorra el importe que habría pagado según su tipo marginal.

### 4. Coste neto por día

```
Coste neto/día = Coste bruto/día × (1 − 6,50 % − IRPF%)
```

### 5. Coste neto total y recuperación

```
Coste neto total = Coste neto/día × Días de huelga
Meses para recuperar = Coste neto total ÷ Aumento mensual neto esperado
```

---

## Tecnología

Fichero único `index.html` con HTML, CSS y JavaScript vanilla. Sin dependencias externas. Funciona directamente en GitHub Pages.
