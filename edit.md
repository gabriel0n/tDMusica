---


---

<h1 id="sistema-de-gestión-de-tienda-de-discos">Sistema de Gestión de Tienda de Discos</h1>
<p>Este proyecto es un <strong>Sistema de Gestión de Tienda de Discos</strong> desarrollado en <strong>Java</strong> utilizando el entorno de desarrollo <strong>NetBeans</strong> y una base de datos relacional en <strong>MySQL XAMPP</strong>. El sistema está diseñado para permitir una administración eficiente de clientes, productos, proveedores y ventas, ofreciendo una experiencia amigable para administradores, cajeros y usuarios finales.</p>
<hr>
<h2 id="características-principales"><strong>Características Principales</strong></h2>
<h3 id="gestión-de-usuarios-y-roles"><strong>Gestión de Usuarios y Roles</strong></h3>
<ul>
<li><strong>Roles disponibles</strong>: Administrador y Cajero.</li>
<li><strong>Validación de permisos</strong> para cada rol, asegurando accesos restringidos a las funciones correspondientes.</li>
<li><strong>Inicio de sesión</strong> con autenticación basada en correo electrónico y contraseña.</li>
</ul>
<h3 id="gestión-de-inventario-de-discos"><strong>Gestión de Inventario de Discos</strong></h3>
<ul>
<li><strong>Operaciones disponibles</strong>:
<ul>
<li>Agregar discos nuevos.</li>
<li>Modificar detalles de los discos (nombre, código, stock, precio, género).</li>
<li>Eliminar discos existentes.</li>
<li>Controlar el stock y la disponibilidad de los discos.</li>
</ul>
</li>
<li><strong>Validación de entradas</strong> en los formularios:
<ul>
<li>Código: Solo letras y números.</li>
<li>Nombre: Solo letras.</li>
<li>Stock: Solo números enteros.</li>
<li>Precio: Números enteros o decimales.</li>
</ul>
</li>
</ul>
<h3 id="gestión-de-clientes"><strong>Gestión de Clientes</strong></h3>
<ul>
<li><strong>Operaciones disponibles</strong>:
<ul>
<li>Agregar nuevos clientes.</li>
<li>Modificar datos de los clientes.</li>
<li>Eliminar clientes.</li>
</ul>
</li>
<li><strong>Validaciones de datos</strong>:
<ul>
<li>RFC: Letras y números.</li>
<li>Nombre: Solo letras.</li>
<li>Teléfono: Solo números.</li>
</ul>
</li>
</ul>
<h3 id="gestión-de-proveedores"><strong>Gestión de Proveedores</strong></h3>
<ul>
<li><strong>Operaciones disponibles</strong>:
<ul>
<li>Agregar nuevos proveedores.</li>
<li>Modificar datos de los proveedores.</li>
<li>Eliminar proveedores.</li>
</ul>
</li>
<li><strong>Validaciones de datos</strong> similares a las de clientes.</li>
</ul>
<h3 id="gestión-de-ventas"><strong>Gestión de Ventas</strong></h3>
<ul>
<li><strong>Registrar ventas</strong> de discos a clientes.</li>
<li><strong>Actualizar el stock automáticamente</strong> después de cada venta.</li>
<li><strong>Eliminar ventas</strong> y recalcular el total de la venta si se eliminan productos.</li>
<li><strong>Control de duplicados</strong> en el código de productos.</li>
</ul>
<h3 id="interfaz-de-usuario"><strong>Interfaz de Usuario</strong></h3>
<ul>
<li><strong>Diseño intuitivo y fácil de usar</strong>.</li>
<li><strong>Validaciones visuales</strong> para evitar errores en los formularios.</li>
<li><strong>Pestañas de navegación</strong> para diferenciar entre roles (Administrador y Cajero).</li>
</ul>
<h3 id="base-de-datos-en-mysql"><strong>Base de Datos en MySQL</strong></h3>
<ul>
<li><strong>Tablas principales</strong>:
<ul>
<li><code>clientes</code>: Información de los clientes.</li>
<li><code>proveedores</code>: Información de los proveedores.</li>
<li><code>productos</code>: Inventario de discos.</li>
<li><code>ventas</code>: Registro de ventas realizadas.</li>
</ul>
</li>
<li><strong>Transacciones seguras</strong> para garantizar la integridad de los datos.</li>
</ul>
<hr>
<h2 id="instrucciones-de-instalación-y-configuración"><strong>Instrucciones de Instalación y Configuración</strong></h2>
<h3 id="requisitos-previos"><strong>Requisitos Previos</strong></h3>
<ul>
<li><strong>Java JDK 8 o superior</strong></li>
<li><strong>NetBeans IDE</strong></li>
<li><strong>XAMPP y MySQL</strong></li>
</ul>
<h3 id="instalación-del-proyecto"><strong>Instalación del Proyecto</strong></h3>
<ol>
<li>
<p><strong>Clonar el repositorio</strong> desde GitHub:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">git</span> clone https://github.com/tuusuario/tienda-discos.git
</code></pre>
</li>
<li>
<p><strong>Abrir el proyecto en NetBeans</strong>:</p>
<ul>
<li>Ve a <code>File &gt; Open Project</code> y selecciona la carpeta del proyecto.</li>
</ul>
</li>
<li>
<p><strong>Configurar la base de datos XAMPP</strong>:</p>
<ul>
<li>Crear una base de datos llamada <code>tienda_discos</code>.</li>
<li>Importar el esquema de base de datos (<code>tienda_discos.sql</code>) que se encuentra en la carpeta <code>database</code> del proyecto.</li>
</ul>
</li>
<li>
<p><strong>Configurar la conexión a la base de datos</strong> en la clase <code>Conexion.java</code>:</p>
<pre class=" language-java"><code class="prism  language-java"><span class="token keyword">public</span> <span class="token keyword">class</span> <span class="token class-name">Conexion</span> <span class="token punctuation">{</span>
    <span class="token keyword">private</span> <span class="token keyword">static</span> <span class="token keyword">final</span> String URL <span class="token operator">=</span> <span class="token string">"jdbc:postgresql://localhost:5432/tienda_discos"</span><span class="token punctuation">;</span>
    <span class="token keyword">private</span> <span class="token keyword">static</span> <span class="token keyword">final</span> String USER <span class="token operator">=</span> <span class="token string">"app_user"</span><span class="token punctuation">;</span>
    <span class="token keyword">private</span> <span class="token keyword">static</span> <span class="token keyword">final</span> String PASSWORD <span class="token operator">=</span> <span class="token string">"app_password"</span><span class="token punctuation">;</span>

    <span class="token keyword">public</span> <span class="token keyword">static</span> Connection <span class="token function">getConnection</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token keyword">throws</span> SQLException <span class="token punctuation">{</span>
        <span class="token keyword">return</span> DriverManager<span class="token punctuation">.</span><span class="token function">getConnection</span><span class="token punctuation">(</span>URL<span class="token punctuation">,</span> USER<span class="token punctuation">,</span> PASSWORD<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
</li>
<li>
<p><strong>Ejecutar el proyecto</strong> desde NetBeans:</p>
<ul>
<li>Haz clic derecho en el proyecto y selecciona <code>Run</code>.</li>
</ul>
</li>
</ol>
<hr>
<h2 id="explicación-de-la-estructura-de-la-base-de-datos"><strong>Explicación de la Estructura de la Base de Datos</strong></h2>
<p>La base de datos está compuesta por las siguientes tablas:</p>
<h3 id="clientes"><strong>1. <code>clientes</code></strong></h3>

<table>
<thead>
<tr>
<th>Columna</th>
<th>Tipo de Dato</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>id</code></td>
<td>SERIAL</td>
<td>Identificador único</td>
</tr>
<tr>
<td><code>rfc</code></td>
<td>VARCHAR(13)</td>
<td>RFC del cliente</td>
</tr>
<tr>
<td><code>nombre</code></td>
<td>VARCHAR(100)</td>
<td>Nombre del cliente</td>
</tr>
<tr>
<td><code>telefono</code></td>
<td>VARCHAR(15)</td>
<td>Teléfono del cliente</td>
</tr>
<tr>
<td><code>direccion</code></td>
<td>VARCHAR(255)</td>
<td>Dirección del cliente</td>
</tr>
</tbody>
</table><h3 id="proveedores"><strong>2. <code>proveedores</code></strong></h3>

<table>
<thead>
<tr>
<th>Columna</th>
<th>Tipo de Dato</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>id</code></td>
<td>SERIAL</td>
<td>Identificador único</td>
</tr>
<tr>
<td><code>rfc</code></td>
<td>VARCHAR(13)</td>
<td>RFC del proveedor</td>
</tr>
<tr>
<td><code>nombre</code></td>
<td>VARCHAR(100)</td>
<td>Nombre del proveedor</td>
</tr>
<tr>
<td><code>telefono</code></td>
<td>VARCHAR(15)</td>
<td>Teléfono del proveedor</td>
</tr>
<tr>
<td><code>direccion</code></td>
<td>VARCHAR(255)</td>
<td>Dirección del proveedor</td>
</tr>
</tbody>
</table><h3 id="productos"><strong>3. <code>productos</code></strong></h3>

<table>
<thead>
<tr>
<th>Columna</th>
<th>Tipo de Dato</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>id</code></td>
<td>SERIAL</td>
<td>Identificador único</td>
</tr>
<tr>
<td><code>codigo</code></td>
<td>VARCHAR(10)</td>
<td>Código único del producto</td>
</tr>
<tr>
<td><code>nombre</code></td>
<td>VARCHAR(100)</td>
<td>Nombre del disco</td>
</tr>
<tr>
<td><code>stock</code></td>
<td>INT</td>
<td>Cantidad disponible</td>
</tr>
<tr>
<td><code>precio</code></td>
<td>DECIMAL(10,2)</td>
<td>Precio del disco</td>
</tr>
</tbody>
</table><h3 id="ventas"><strong>4. <code>ventas</code></strong></h3>

<table>
<thead>
<tr>
<th>Columna</th>
<th>Tipo de Dato</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>id</code></td>
<td>SERIAL</td>
<td>Identificador único</td>
</tr>
<tr>
<td><code>id_cliente</code></td>
<td>INT</td>
<td>Clave foránea a <code>clientes</code></td>
</tr>
<tr>
<td><code>fecha</code></td>
<td>DATE</td>
<td>Fecha de la venta</td>
</tr>
<tr>
<td><code>total</code></td>
<td>DECIMAL(10,2)</td>
<td>Total de la venta</td>
</tr>
</tbody>
</table><hr>
<h2 id="🗂️-estructura-de-la-base-de-datos">🗂️ <strong>Estructura de la Base de Datos</strong></h2>
<h3 id="tablas-principales"><strong>Tablas Principales</strong></h3>
<ol>
<li><strong><code>cliente</code></strong>: Almacena información de los clientes.</li>
<li><strong><code>proveedor</code></strong>: Almacena información de los proveedores.</li>
<li><strong><code>producto</code></strong>: Contiene detalles de los discos disponibles.</li>
<li><strong><code>venta</code></strong>: Registra cada venta realizada.</li>
<li><strong><code>detalle_venta</code></strong>: Contiene detalles individuales de cada producto vendido en una venta.</li>
</ol>
<hr>
<h2 id="📦-resumen-de-clases">📦 <strong>Resumen de Clases</strong></h2>
<h3 id="clase-cliente"><strong>1. Clase <code>Cliente</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Gestiona los datos de los clientes.</li>
<li><strong>Atributos</strong>:
<ul>
<li><code>id</code>: Identificador único.</li>
<li><code>rfc</code>: RFC del cliente.</li>
<li><code>nombre</code>: Nombre del cliente.</li>
<li><code>telefono</code>: Teléfono del cliente.</li>
<li><code>direccion</code>: Dirección del cliente.</li>
</ul>
</li>
</ul>
<h3 id="clase-proveedor"><strong>2. Clase <code>Proveedor</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Maneja los datos de los proveedores.</li>
<li><strong>Atributos</strong> similares a los de <code>Cliente</code>.</li>
</ul>
<h3 id="clase-producto"><strong>3. Clase <code>Producto</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Gestiona los discos disponibles para la venta.</li>
<li><strong>Atributos</strong>:
<ul>
<li><code>codigo</code>: Código único del producto.</li>
<li><code>nombre</code>: Nombre del disco.</li>
<li><code>stock</code>: Cantidad disponible.</li>
<li><code>precio</code>: Precio del disco.</li>
</ul>
</li>
</ul>
<h3 id="clase-venta"><strong>4. Clase <code>Venta</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Gestiona las ventas realizadas en la tienda.</li>
<li><strong>Atributos</strong>:
<ul>
<li><code>id</code>: Identificador único.</li>
<li><code>cliente_id</code>: ID del cliente que realiza la compra.</li>
<li><code>fecha</code>: Fecha de la venta.</li>
<li><code>total</code>: Importe total de la venta.</li>
</ul>
</li>
</ul>
<p><strong>Clase: MainFrame.java</strong></p>
<ul>
<li><strong>Responsabilidad</strong>: Esta es la clase principal que contiene la interfaz gráfica del sistema (GUI). Permite a los usuarios interactuar con el sistema mediante formularios para agregar productos, registrar ventas, etc.</li>
<li><strong>Métodos principales</strong>:
<ul>
<li><code>iniciarAplicacion()</code>: Inicia la aplicación y muestra la ventana principal.</li>
<li><code>mostrarFormularioClientes()</code>: Muestra el formulario para agregar o editar clientes.</li>
<li><code>mostrarFormularioVentas()</code>: Muestra el formulario para registrar ventas.</li>
</ul>
</li>
</ul>
<p><strong>Clase: ConexionBD.java</strong></p>
<ul>
<li><strong>Responsabilidad</strong>: Gestiona la conexión con la base de datos PostgreSQL. Establece la conexión utilizando JDBC y maneja las operaciones de consulta, inserción, actualización y eliminación.</li>
<li><strong>Métodos principales</strong>:
<ul>
<li><code>conectar()</code>: Establece la conexión con la base de datos.</li>
<li><code>desconectar()</code>: Cierra la conexión con la base de datos.</li>
</ul>
</li>
</ul>
<hr>
<h2 id="🖼️-capturas-de-pantalla">🖼️ <strong>Capturas de Pantalla</strong></h2>
<h2 id="🖥️-pantalla-de-inicio-de-sesión">🖥️ Pantalla de Inicio de Sesión</h2>
<p>Esta es la <strong>pantalla de inicio de sesión</strong> para el sistema de gestión de la tienda de discos .</p>
<p>![Inicio de sesión para el administrador<br>
(<a href="https://photos.app.goo.gl/rUgxLth9AYpRUEin9">https://photos.app.goo.gl/rUgxLth9AYpRUEin9</a>)</p>
<h3 id="📌-descripción-de-la-interfaz">📌 <strong>Descripción de la Interfaz</strong></h3>
<ol>
<li>
<p><strong>Encabezado con Roles</strong>:</p>
<ul>
<li>Dos pestañas en la parte superior para seleccionar el rol de usuario:
<ul>
<li><strong>Administrador</strong>.</li>
<li><strong>Cajero</strong>.</li>
</ul>
</li>
<li>Esto permite elegir el tipo de usuario para acceder al sistema con permisos específicos.</li>
</ul>
</li>
<li>
<p><strong>Campos de Inicio de Sesión</strong>:</p>
<ul>
<li><strong>Correo Electrónico</strong>: Un campo de texto para introducir el correo electrónico del usuario.</li>
<li><strong>Contraseña</strong>: Un campo de texto para introducir la contraseña del usuario.</li>
</ul>
</li>
<li>
<p><strong>Botón de Ingreso</strong>:</p>
<ul>
<li>Un botón con un icono de usuario y el texto <strong>“Ingresar”</strong>.</li>
<li>Al hacer clic en este botón, se valida la información ingresada y se permite el acceso al sistema.</li>
</ul>
</li>
</ol>
<h3 id="🧩-funcionalidad-del-código">🧩 <strong>Funcionalidad del Código</strong></h3>
<p>La funcionalidad de esta pantalla está diseñada para validar los datos del usuario e iniciar sesión según su rol seleccionado.</p>
<h2 id="interfaz-de-inicio-de-sesión-para-tienda-de-discos">Interfaz de Inicio de Sesión para Tienda de Discos</h2>
<p>Esta imagen representa la interfaz de inicio de sesión del sistema para la tienda de discos.</p>
<hr>
<h3 id="descripción-visual-del-inicio-de-sesión-del-rol-cajero">Descripción Visual del inicio de sesión del rol cajero</h3>
<p>![Rol cajero]<br>
(<a href="https://photos.app.goo.gl/uCtqhGu4pT2eF7a87">https://photos.app.goo.gl/uCtqhGu4pT2eF7a87</a>)</p>
<ul>
<li>
<p><strong>Pestañas Superiores</strong>:</p>
<ul>
<li><strong>Administrador</strong>: Permite seleccionar el modo de inicio de sesión para administradores.</li>
<li><strong>Cajero</strong>: Permite seleccionar el modo de inicio de sesión para cajeros</li>
</ul>
</li>
<li>
<p><strong>Campos de Entrada</strong>:</p>
<ul>
<li><strong>Correo Electrónico</strong>:<br>
Un campo de texto para ingresar el correo electrónico del usuario.</li>
<li><strong>Contraseña</strong>:<br>
Un campo de texto para ingresar la contraseña del usuario.</li>
</ul>
</li>
<li>
<p><strong>Botón de Ingreso</strong>:</p>
<ul>
<li>Botón con un icono de una persona y una flecha, etiquetado como <strong>“Ingresar”</strong>. Al hacer clic en este botón, el sistema valida las credenciales introducidas y permite el acceso correspondiente.</li>
</ul>
</li>
</ul>
<hr>
<h2 id="interfaz-de-gestión-de-ventas-para-tienda-de-discos">Interfaz de Gestión de Ventas para Tienda de Discos</h2>
<p>Esta sección de la aplicación corresponde a la <strong>gestión de ventas</strong> en la tienda de discos. La interfaz permite realizar nuevas ventas, gestionar clientes, proveedores, productos, y generar facturas en formato PDF.</p>
<hr>
<h3 id="descripción-visual">Descripción Visual</h3>
<p>![Cajero]<br>
(<a href="https://photos.app.goo.gl/JAKz8bAJJioMW3jj9">https://photos.app.goo.gl/JAKz8bAJJioMW3jj9</a>)</p>
<hr>
<h3 id="componentes-de-la-interfaz">Componentes de la Interfaz</h3>
<ol>
<li>
<p><strong>Encabezado</strong>:</p>
<ul>
<li><strong>Información de Contacto</strong>:
<ul>
<li><strong>Teléfono</strong>: <code>9515323334</code></li>
<li><strong>Mensaje de Información</strong>:<br>
“Para dudas o información puede comunicarse al número 9512044541.”</li>
<li><strong>Ubicación</strong>: Oaxaca, México.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Formulario de Venta</strong>:</p>
<ul>
<li>
<p><strong>Campos</strong>:</p>
<ul>
<li><strong>Código</strong>: <code>lp006</code> – Código del disco.</li>
<li><strong>Descripción</strong>: <code>Hotel California</code> – Título del disco.</li>
<li><strong>Cantidad</strong>: <code>3</code> – Número de unidades seleccionadas.</li>
<li><strong>Precio</strong>: <code>30.0</code> – Precio unitario del disco.</li>
<li><strong>Stock Disponible</strong>: <code>9</code> – Cantidad disponible en inventario.</li>
</ul>
</li>
<li>
<p><strong>Botón “Eliminar”</strong>:<br>
Un botón con un icono de carrito y la etiqueta <strong>“Eliminar”</strong> para quitar el producto seleccionado de la venta.</p>
</li>
</ul>
</li>
<li>
<p><strong>Tabla de Productos en la Venta</strong>:</p>
<ul>
<li><strong>Columnas</strong>:
<ul>
<li><strong>Código</strong>: Identificador del producto (<code>lp007</code>, <code>lp023</code>).</li>
<li><strong>Descripción</strong>: Título del disco (<code>Thriller</code>, <code>this is it</code>).</li>
<li><strong>Cantidad</strong>: Número de unidades (<code>4</code>, <code>10</code>).</li>
<li><strong>Precio</strong>: Precio unitario (<code>50.0</code>, <code>40.0</code>).</li>
<li><strong>Total</strong>: Total por producto (<code>200.0</code>, <code>400.0</code>).</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Sección del Cliente</strong>:</p>
<ul>
<li><strong>RFC</strong>: <code>123456789</code> – Registro Federal de Contribuyentes del cliente.</li>
<li><strong>Nombre</strong>: <code>Juan Pérez</code> – Nombre del cliente.</li>
<li><strong>Etiqueta “Administrador”</strong>: Indica el rol del usuario actual.</li>
</ul>
</li>
<li>
<p><strong>Opciones de Facturación</strong>:</p>
<ul>
<li>
<p><strong>Campo “Enviar Factura al Correo”</strong>:<br>
Permite ingresar un correo electrónico para enviar la factura.</p>
</li>
<li>
<p><strong>Total a Pagar</strong>:<br>
Muestra el total de la venta: <code>600.00</code>.</p>
</li>
<li>
<p><strong>Botones</strong>:</p>
<ul>
<li><strong>Enviar Correo</strong>:<br>
Botón para enviar la factura por correo electrónico.</li>
<li><strong>Pagar y Generar PDF</strong>:<br>
Botón para registrar el pago y generar una factura en formato PDF.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Menú Lateral Derecho</strong>:</p>
<ul>
<li><strong>Botones de Acción</strong>:
<ul>
<li><strong>Nueva Venta</strong>: Icono de carrito – Permite iniciar una nueva venta.</li>
<li><strong>Clientes</strong>: Icono de personas – Acceso al módulo de clientes.</li>
<li><strong>Proveedor</strong>: Icono de archivo – Acceso al módulo de proveedores.</li>
<li><strong>Productos</strong>: Icono de disco – Acceso al módulo de productos.</li>
<li><strong>Ventas</strong>: Icono de dólar – Acceso al historial de ventas.</li>
</ul>
</li>
</ul>
</li>
</ol>
<h2 id="interfaz-de-gestión-de-clientes">Interfaz de Gestión de Clientes</h2>
<p>Esta sección de la aplicación corresponde a la <strong>gestión de clientes</strong> en la tienda de discos. Permite agregar, editar y eliminar clientes, así como visualizar la lista de clientes almacenados en la base de datos.</p>
<hr>
<h3 id="descripción-visual-1">Descripción Visual</h3>
<p>![Administración de los clientes<br>
(<a href="https://photos.app.goo.gl/fAEkcXUbPmDKTSV26">https://photos.app.goo.gl/fAEkcXUbPmDKTSV26</a>)</p>
<hr>
<h3 id="componentes-de-la-interfaz-1">Componentes de la Interfaz</h3>
<ol>
<li>
<p><strong>Formulario de Cliente</strong>:</p>
<ul>
<li><strong>Campos de Entrada</strong>:
<ul>
<li><strong>RFC</strong>: Campo para ingresar el Registro Federal de Contribuyentes del cliente.</li>
<li><strong>Nombre</strong>: Campo para ingresar el nombre del cliente.</li>
<li><strong>Teléfono</strong>: Campo para ingresar el número telefónico del cliente.</li>
<li><strong>Dirección</strong>: Campo para ingresar la dirección del cliente.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Botones de Acción</strong>:</p>
<ul>
<li>
<p><strong>Guardar Cliente</strong>:<br>
Permite guardar un nuevo cliente en la base de datos.</p>
</li>
<li>
<p><strong>Eliminar Cliente</strong>:<br>
Elimina el cliente seleccionado de la tabla.</p>
</li>
<li>
<p><strong>Editar Cliente</strong>:<br>
Permite editar los datos del cliente seleccionado.</p>
</li>
<li>
<p><strong>Nuevo Cliente</strong>:<br>
Limpia los campos para registrar un nuevo cliente.</p>
</li>
</ul>
</li>
<li>
<p><strong>Tabla de Clientes</strong>:</p>
<ul>
<li><strong>Descripción de las Columnas</strong>:
<ul>
<li><strong>RFC</strong>: Identificación del cliente.</li>
<li><strong>Nombre</strong>: Nombre completo del cliente.</li>
<li><strong>Teléfono</strong>: Número telefónico del cliente.</li>
<li><strong>Dirección</strong>: Dirección del cliente.</li>
<li><strong>ID</strong>: Identificador único del cliente en la base de datos.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Menú Lateral Derecho</strong>:</p>
<ul>
<li><strong>Botones de Navegación</strong>:
<ul>
<li><strong>Nueva Venta</strong>: Accede al módulo de ventas.</li>
<li><strong>Clientes</strong>: Accede al módulo de gestión de clientes (actualmente activo).</li>
<li><strong>Proveedor</strong>: Accede al módulo de proveedores.</li>
<li><strong>Productos</strong>: Accede al módulo de gestión de productos.</li>
<li><strong>Ventas</strong>: Accede al historial de ventas.</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr>
<h2 id="interfaz-de-gestión-de-proveedores">Interfaz de Gestión de Proveedores</h2>
<p>La interfaz de gestión de proveedores permite administrar los datos de proveedores en la tienda de discos . Esta sección facilita el registro, actualización y eliminación de proveedores, así como la consulta de los datos almacenados en la base de datos.</p>
<hr>
<h3 id="descripción-visual-2">Descripción Visual</h3>
<h2 id="proveedoreshttpsphotos.app.goo.glpmqf19key9tafy2q6">![Proveedores<br>
(<a href="https://photos.app.goo.gl/Pmqf19key9tafy2q6">https://photos.app.goo.gl/Pmqf19key9tafy2q6</a>)</h2>
<h3 id="componentes-de-la-interfaz-2">Componentes de la Interfaz</h3>
<ol>
<li>
<p><strong>Formulario de Entrada</strong>:</p>
<ul>
<li><strong>RFC</strong>: Campo para ingresar el Registro Federal de Contribuyentes del proveedor.</li>
<li><strong>Nombre</strong>: Campo para ingresar el nombre del proveedor.</li>
<li><strong>Teléfono</strong>: Campo para ingresar el número telefónico del proveedor.</li>
<li><strong>Dirección</strong>: Campo para ingresar la dirección del proveedor.</li>
</ul>
</li>
<li>
<p><strong>Botones de Acción</strong>:</p>
<ul>
<li><strong>Guardar</strong>: Guarda los datos del proveedor en la base de datos.</li>
<li><strong>Editar</strong>: Permite modificar los datos del proveedor seleccionado.</li>
<li><strong>Eliminar</strong>: Elimina el proveedor seleccionado de la base de datos.</li>
<li><strong>Agregar</strong>: Limpia los campos del formulario para ingresar un nuevo proveedor.</li>
</ul>
</li>
<li>
<p><strong>Tabla de Proveedores</strong>:</p>
<ul>
<li>Muestra una lista de proveedores con los siguientes campos:
<ul>
<li><strong>RFC</strong>: Registro Federal de Contribuyentes del proveedor.</li>
<li><strong>Nombre</strong>: Nombre del proveedor.</li>
<li><strong>Teléfono</strong>: Número telefónico del proveedor.</li>
<li><strong>Dirección</strong>: Dirección del proveedor.</li>
<li><strong>ID</strong>: Identificador único del proveedor.</li>
</ul>
</li>
</ul>
<p>La tabla permite visualizar los proveedores almacenados en la base de datos y facilita su selección para realizar operaciones de edición o eliminación.</p>
</li>
<li>
<p><strong>Menú Lateral Derecho</strong>:</p>
<ul>
<li><strong>Botones de Navegación</strong>:
<ul>
<li><strong>Nueva Venta</strong>: Accede al módulo de ventas para realizar nuevas transacciones.</li>
<li><strong>Clientes</strong>: Accede al módulo de gestión de clientes.</li>
<li><strong>Proveedor</strong>: Accede al módulo de gestión de proveedores (actualmente activo).</li>
<li><strong>Productos</strong>: Accede al módulo de gestión de productos.</li>
<li><strong>Ventas</strong>: Accede al historial de ventas.</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr>
<h3 id="funcionalidad">Funcionalidad</h3>
<ul>
<li>
<p><strong>Agregar Proveedor</strong>:<br>
Permite registrar nuevos proveedores en el sistema al llenar los campos del formulario y presionar el botón <strong>Guardar</strong>.</p>
</li>
<li>
<p><strong>Editar Proveedor</strong>:<br>
Permite modificar la información de un proveedor existente seleccionándolo en la tabla, cargando sus datos en el formulario y presionando el botón <strong>Editar</strong>.</p>
</li>
<li>
<p><strong>Eliminar Proveedor</strong>:<br>
Elimina un proveedor seleccionado de la tabla y de la base de datos al presionar el botón <strong>Eliminar</strong>.</p>
</li>
<li>
<p><strong>Consultar Proveedores</strong>:<br>
La tabla se actualiza automáticamente al realizar operaciones de agregar, editar o eliminar proveedores, mostrando siempre la información más reciente almacenada en la base de datos.</p>
</li>
</ul>
<hr>
<h3 id="notas">Notas</h3>
<ul>
<li>
<p><strong>Validaciones</strong>:<br>
Se recomienda implementar validaciones para asegurar que los campos obligatorios se completen y que los datos ingresados sigan el formato adecuado.</p>
</li>
<li>
<p><strong>Interfaz Amigable</strong>:<br>
La disposición de los botones y formularios está diseñada para facilitar una navegación intuitiva y eficiente.</p>
</li>
</ul>
<hr>
<h2 id="📝-notas-adicionales">📝 <strong>Notas Adicionales</strong></h2>
<ul>
<li><strong>Manejo de Excepciones</strong>: Se implementa validación para evitar errores en campos de texto como RFC, nombres, y precios.</li>
<li><strong>Seguridad</strong>: Se recomienda no almacenar contraseñas en texto plano en el código fuente.</li>
<li><strong>Envío de Correos</strong>: Si el sistema incluye envío de correos electrónicos, asegúrate de no exponer claves API en el repositorio.</li>
</ul>
<hr>
<h2 id="interfaz-de-gestión-de-productos">Interfaz de Gestión de Productos</h2>
<p>La interfaz de gestión de productos facilita la administración del inventario de discos en la tienda . Permite realizar operaciones de registro, actualización y eliminación de productos, así como consultar los datos almacenados en la base de datos.</p>
<hr>
<h3 id="descripción-visual-3">Descripción Visual</h3>
<p>![Productos]<br>
(<a href="https://photos.app.goo.gl/yx7396Q3Zo4kBosT7">https://photos.app.goo.gl/yx7396Q3Zo4kBosT7</a>)</p>
<hr>
<h3 id="componentes-de-la-interfaz-3">Componentes de la Interfaz</h3>
<ol>
<li>
<p><strong>Formulario de Entrada</strong>:</p>
<ul>
<li><strong>Código</strong>: Campo para ingresar el código único del producto.</li>
<li><strong>Nombre</strong>: Campo para ingresar el nombre del disco.</li>
<li><strong>Stock</strong>: Campo para ingresar la cantidad disponible del producto.</li>
<li><strong>Precio</strong>: Campo para ingresar el precio del disco.</li>
<li><strong>Proveedor</strong>: Menú desplegable para seleccionar el proveedor asociado al producto.</li>
</ul>
</li>
<li>
<p><strong>Botones de Acción</strong>:</p>
<ul>
<li><strong>Guardar</strong>: Guarda los datos del producto en la base de datos.</li>
<li><strong>Editar</strong>: Permite modificar los datos del producto seleccionado.</li>
<li><strong>Eliminar Producto</strong>: Elimina el producto seleccionado de la base de datos.</li>
<li><strong>Nuevo Producto</strong>: Limpia los campos del formulario para ingresar un nuevo producto.</li>
</ul>
</li>
<li>
<p><strong>Tabla de Productos</strong>:</p>
<ul>
<li>Muestra una lista de los productos almacenados en la base de datos con los siguientes campos:
<ul>
<li><strong>Código</strong>: Código único que identifica el producto.</li>
<li><strong>Nombre</strong>: Nombre del disco.</li>
<li><strong>Stock</strong>: Cantidad de unidades disponibles en el inventario.</li>
<li><strong>Precio</strong>: Precio del producto.</li>
<li><strong>Proveedor</strong>: Nombre del proveedor asociado al producto.</li>
<li><strong>ID</strong>: Identificador único del producto en la base de datos.</li>
</ul>
</li>
</ul>
<p>La tabla permite visualizar los productos y facilita su selección para realizar operaciones de edición o eliminación.</p>
</li>
<li>
<p><strong>Menú Lateral Derecho</strong>:</p>
<ul>
<li><strong>Botones de Navegación</strong>:
<ul>
<li><strong>Nueva Venta</strong>: Accede al módulo para realizar nuevas ventas.</li>
<li><strong>Clientes</strong>: Accede al módulo de gestión de clientes.</li>
<li><strong>Proveedor</strong>: Accede al módulo de gestión de proveedores.</li>
<li><strong>Productos</strong>: Accede al módulo actual de gestión de productos.</li>
<li><strong>Ventas</strong>: Accede al historial de ventas.</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr>
<h3 id="funcionalidad-1">Funcionalidad</h3>
<ul>
<li>
<p><strong>Agregar Producto</strong>:<br>
Permite registrar nuevos productos en el sistema rellenando los campos del formulario y presionando el botón <strong>Guardar</strong>.</p>
</li>
<li>
<p><strong>Editar Producto</strong>:<br>
Permite modificar los datos de un producto existente seleccionándolo en la tabla, cargando sus datos en el formulario y presionando el botón <strong>Editar</strong>.</p>
</li>
<li>
<p><strong>Eliminar Producto</strong>:<br>
Elimina un producto seleccionado de la tabla y de la base de datos al presionar el botón <strong>Eliminar Producto</strong>.</p>
</li>
<li>
<p><strong>Consultar Productos</strong>:<br>
La tabla se actualiza automáticamente al realizar operaciones de agregar, editar o eliminar productos, mostrando siempre la información más reciente almacenada en la base de datos.</p>
</li>
<li>
<p><strong>Navegación Rápida</strong>:<br>
Utiliza los botones del menú lateral derecho para acceder rápidamente a otros módulos del sistema.</p>
</li>
</ul>
<hr>
<h3 id="notas-1">Notas</h3>
<ul>
<li>
<p><strong>Validaciones</strong>:<br>
Se recomienda implementar validaciones en los campos del formulario para asegurar que se ingresen datos correctos, como números enteros en el campo <strong>Stock</strong> y valores decimales en el campo <strong>Precio</strong>.</p>
</li>
<li>
<p><strong>Interfaz Amigable</strong>:<br>
La disposición clara y ordenada de los componentes facilita la navegación y el uso eficiente de la interfaz por parte del usuario.</p>
</li>
</ul>
<hr>
<h2 id="interfaz-de-gestión-de-ventas">Interfaz de Gestión de Ventas</h2>
<p>La interfaz de gestión de ventas facilita el seguimiento y control de las transacciones realizadas en la tienda. Permite consultar los detalles de las ventas registradas en la base de datos, mostrando información relevante para una gestión eficiente.</p>
<hr>
<h3 id="descripción-visual-4">Descripción Visual</h3>
<p>![Historial de las ventas<br>
(<a href="https://photos.app.goo.gl/JaM9CcbrGhEv9eAg8">https://photos.app.goo.gl/JaM9CcbrGhEv9eAg8</a>)</p>
<hr>
<h3 id="componentes-de-la-interfaz-4">Componentes de la Interfaz</h3>
<ol>
<li>
<p><strong>Encabezado Informativo</strong>:</p>
<ul>
<li>Información de contacto de la tienda:
<ul>
<li><strong>Nombre</strong>: GASEDY FAIR RECORDS.</li>
<li><strong>Teléfono</strong>: Número de contacto para consultas.</li>
<li><strong>Ubicación</strong>: Oaxaca, México.</li>
<li><strong>Mensaje de Ayuda</strong>: Sección con indicación para dudas o información adicional.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Tabla de Ventas</strong>:</p>
<ul>
<li>Muestra una lista de todas las ventas registradas en la base de datos. Cada fila de la tabla representa una venta específica con los siguientes campos:
<ul>
<li><strong>ID</strong>: Identificador único de la venta.</li>
<li><strong>Cliente</strong>: Nombre del cliente que realizó la compra.</li>
<li><strong>Vendedor</strong>: Nombre del vendedor que registró la venta.</li>
<li><strong>Total</strong>: Monto total de la venta.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Menú Lateral Derecho</strong>:</p>
<ul>
<li><strong>Botones de Navegación</strong> para acceder a otros módulos del sistema:
<ul>
<li><strong>Nueva Venta</strong>: Accede al módulo para registrar una nueva venta.</li>
<li><strong>Clientes</strong>: Accede al módulo de gestión de clientes.</li>
<li><strong>Proveedor</strong>: Accede al módulo de gestión de proveedores.</li>
<li><strong>Productos</strong>: Accede al módulo de gestión de productos.</li>
<li><strong>Ventas</strong>: Accede al módulo actual de gestión de ventas.</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr>
<h3 id="funcionalidad-2">Funcionalidad</h3>
<ul>
<li>
<p><strong>Consulta de Ventas</strong>:<br>
La tabla permite visualizar el historial de ventas con detalles de cada transacción. Facilita el seguimiento de las compras realizadas por cada cliente y el desempeño de los vendedores.</p>
</li>
<li>
<p><strong>Gestión de Transacciones</strong>:<br>
La información detallada en la tabla permite revisar los montos totales de cada venta, ayudando en tareas de auditoría y análisis de ventas.</p>
</li>
<li>
<p><strong>Navegación Rápida</strong>:<br>
Utiliza los botones del menú lateral para acceder a otros módulos del sistema sin necesidad de cerrar la interfaz actual.</p>
</li>
</ul>
<hr>
<h3 id="notas-2">Notas</h3>
<ul>
<li>
<p><strong>Actualización Automática</strong>:<br>
La tabla se actualiza automáticamente después de registrar una nueva venta, asegurando que siempre se muestre la información más reciente.</p>
</li>
<li>
<p><strong>Interfaz Intuitiva</strong>:<br>
El diseño limpio y estructurado permite al usuario localizar rápidamente la información necesaria y facilita el manejo de la interfaz.</p>
</li>
</ul>
<hr>
<h2 id="descripción-del-pdf-de-factura-generada-al-pagar">Descripción del PDF de Factura Generada al Pagar</h2>
<p>Este PDF es generado automáticamente por el sistema de gestión de ventas de <strong>GAISEY RECORD FAIR</strong> después de completar una compra. Sirve como comprobante de venta para el cliente y facilita el seguimiento de transacciones.</p>
<hr>
<h3 id="ejemplo-visual-del-pdf-generado">Ejemplo Visual del PDF Generado</h3>
<p>![PDF<br>
(<a href="https://photos.app.goo.gl/33Yvjz7XNnPCHuTa7">https://photos.app.goo.gl/33Yvjz7XNnPCHuTa7</a>)</p>
<hr>
<h3 id="componentes-del-pdf">Componentes del PDF</h3>
<ol>
<li>
<p><strong>Encabezado</strong>:</p>
<ul>
<li><strong>Nombre de la tienda</strong>:
<ul>
<li><strong>GAISEY RECORD FAIR</strong></li>
</ul>
</li>
<li><strong>Teléfono de contacto</strong>:
<ul>
<li>Número de teléfono para consultas y soporte.</li>
</ul>
</li>
<li><strong>Dirección</strong>:
<ul>
<li>Ubicación de la tienda en <strong>Oaxaca, México</strong>.</li>
</ul>
</li>
<li><strong>Descripción del negocio</strong>:
<ul>
<li>Se indica que es una distribuidora de discos.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Datos del Cliente</strong>:<br>
Sección reservada para capturar los datos del cliente que realiza la compra:</p>
<ul>
<li><strong>RFC</strong>: Registro Federal de Contribuyentes del cliente.</li>
<li><strong>Nombre</strong>: Nombre completo del cliente.</li>
<li><strong>Dirección</strong>: Dirección del cliente.</li>
</ul>
</li>
<li>
<p><strong>Tabla de Productos Comprados</strong>:<br>
La tabla muestra un desglose detallado de los productos adquiridos:</p>
<ul>
<li><strong>Código</strong>: Identificador único del producto.</li>
<li><strong>Descripción</strong>: Nombre del producto (por ejemplo, el título del álbum).</li>
<li><strong>Cantidad</strong>: Número de unidades compradas.</li>
<li><strong>Precio Unitario (Precio U.)</strong>: Costo de una unidad del producto.</li>
<li><strong>Precio Total (Precio T.)</strong>: Resultado de multiplicar la cantidad por el precio unitario.</li>
</ul>
</li>
<li>
<p><strong>Resumen de Pago</strong>:</p>
<ul>
<li><strong>Total a Pagar</strong>:
<ul>
<li>Muestra el monto total que debe pagar el cliente por la compra realizada.</li>
<li>Ejemplo: <code>Total a Pagar: 200.00</code>.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Sección de Firma</strong>:</p>
<ul>
<li><strong>Cancelación y Firma</strong>:<br>
Espacio para que el cliente o el encargado de la venta firme como confirmación de la transacción.</li>
</ul>
</li>
</ol>
<hr>
<h3 id="funcionalidad-del-pdf">Funcionalidad del PDF</h3>
<ul>
<li>
<p><strong>Generación Automática</strong>:<br>
Se genera automáticamente al momento de realizar una venta y completar el pago en el sistema.</p>
</li>
<li>
<p><strong>Propósito</strong>:</p>
<ul>
<li>Sirve como comprobante para el cliente.</li>
<li>Permite llevar un registro digital de las ventas realizadas.</li>
</ul>
</li>
<li>
<p><strong>Formato Estandarizado</strong>:<br>
La estructura del PDF facilita su lectura rápida y clara, con detalles organizados en secciones bien definidas.</p>
</li>
<li>
<p><strong>Entrega Digital</strong>:<br>
Puede enviarse automáticamente al correo electrónico del cliente mediante la función de envío de correos integrados en el sistema.</p>
</li>
</ul>
<hr>
<h3 id="notas-3">Notas</h3>
<ul>
<li>
<p><strong>Cumplimiento Fiscal</strong>:<br>
El diseño del PDF incluye los campos necesarios para cumplir con los requisitos fiscales y proporcionar información detallada para fines de facturación.</p>
</li>
<li>
<p><strong>Personalización</strong>:<br>
La información del cliente se rellena automáticamente desde la base de datos para asegurar precisión y evitar errores manuales.</p>
</li>
</ul>
<hr>
<h2 id="💻-tecnologías-utilizadas">💻 <strong>Tecnologías Utilizadas</strong></h2>
<h2 id="resumen-de-clases-y-responsabilidades"><strong>Resumen de Clases y Responsabilidades</strong></h2>
<h3 id="conexion"><strong>1. <code>Conexion</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Manejar la conexión con la base de datos XAMPP.</li>
</ul>
<h3 id="cliente"><strong>2. <code>Cliente</code></strong></h3>
<ul>
<li><strong>Atributos</strong>: <code>id</code>, <code>rfc</code>, <code>nombre</code>, <code>telefono</code>, <code>direccion</code>.</li>
<li><strong>Métodos</strong>: Getters y setters para manejar los datos del cliente.</li>
</ul>
<h3 id="proveedor"><strong>3. <code>Proveedor</code></strong></h3>
<ul>
<li><strong>Atributos</strong>: <code>id</code>, <code>rfc</code>, <code>nombre</code>, <code>telefono</code>, <code>direccion</code>.</li>
<li><strong>Métodos</strong>: Getters y setters para manejar los datos del proveedor.</li>
</ul>
<h3 id="producto"><strong>4. <code>Producto</code></strong></h3>
<ul>
<li><strong>Atributos</strong>: <code>id</code>, <code>codigo</code>, <code>nombre</code>, <code>stock</code>, <code>precio</code>.</li>
<li><strong>Métodos</strong>: Getters y setters para manejar los datos del producto.</li>
</ul>
<h3 id="venta"><strong>5. <code>Venta</code></strong></h3>
<ul>
<li><strong>Atributos</strong>: <code>id</code>, <code>id_cliente</code>, <code>fecha</code>, <code>total</code>.</li>
<li><strong>Métodos</strong>: Registrar ventas, eliminar ventas y actualizar el stock.</li>
</ul>
<h3 id="login"><strong>6. <code>Login</code></strong></h3>
<ul>
<li><strong>Responsabilidad</strong>: Validar el inicio de sesión para administradores y cajeros.</li>
</ul>
<hr>
<h2 id="tecnologías-utilizadas"><strong>Tecnologías Utilizadas</strong></h2>
<ul>
<li><strong>Lenguaje de Programación</strong>: Java</li>
<li><strong>Entorno de Desarrollo</strong>: NetBeans</li>
<li><strong>Base de Datos</strong>: MySQL XAMPP</li>
<li><strong>Bibliotecas</strong>:
<ul>
<li><code>javax.swing</code> para la interfaz gráfica.</li>
<li><code>java.sql</code> para la conexión y manejo de la base de datos.</li>
</ul>
</li>
</ul>
<hr>
<hr>
<h2 id="notas-finales"><strong>Notas Finales</strong></h2>
<p>Este sistema permite una administración eficiente de una tienda de discos, cubriendo desde la gestión de inventario hasta la realización de ventas y el control de clientes y proveedores. El código está modularizado para facilitar futuras ampliaciones y mantenimiento del proyecto.</p>

