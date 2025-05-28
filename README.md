# 📦 Formato del segmento TCP

Un segmento TCP (Transmission Control Protocol) es una unidad de datos que permite la **comunicación confiable** entre dos dispositivos. Su encabezado contiene varios campos importantes que controlan la transmisión de los datos.

## 🧩 Campos principales del encabezado TCP

### 1. Puerto de origen (16 bits)
- Indica el número de puerto del **host emisor**.
- Identifica la aplicación que **envía** los datos.

### 2. Puerto de destino (16 bits)
- Indica el número de puerto del **host receptor**.
- Identifica la aplicación que **recibe** los datos.

### 3. Número de secuencia (32 bits)
- Indica el número de secuencia del **primer byte de datos** en este segmento.
- Es usado para **reensamblar los datos en orden** en el destino.

### 4. Número de acuse de recibo (Acknowledgment Number, 32 bits)
- Válido solo si el bit ACK está activado.
- Indica el **siguiente número de secuencia** que el receptor espera recibir.

### 5. Longitud del encabezado (Data Offset, 4 bits)
- Especifica la longitud del encabezado TCP.
- Se mide en palabras de 32 bits (múltiplos de 4 bytes).

### 6. Bits de control o flags (6 bits principales)
| Bit | Nombre | Función |
|-----|--------|---------|
| URG | Urgente | Datos urgentes presentes |
| ACK | Acknowledge | Campo de acuse de recibo válido |
| PSH | Push | Solicita entrega inmediata al receptor |
| RST | Reset | Reinicia la conexión |
| SYN | Synchronize | Inicia una conexión |
| FIN | Final | Termina una conexión |

### 7. Tamaño de la ventana (16 bits)
- Cantidad de datos (en bytes) que el receptor está dispuesto a aceptar.
- Se usa para el **control de flujo**.

### 8. Checksum (16 bits)
- Campo de verificación de errores.
- Incluye el encabezado TCP, los datos y una pseudo-cabecera de IP.

### 9. Puntero urgente (Urgent Pointer, 16 bits)
- Válido si el bit URG está activo.
- Indica hasta dónde llegan los datos urgentes dentro del segmento.

### 10. Opciones (opcional, variable)
- Campo adicional para características como:
  - Tamaño máximo de segmento (MSS)
  - Marcas de tiempo (timestamps)
  - Ventana escalable, entre otros.

---

## 📄 Estructura del encabezado TCP (visual simplificada)

