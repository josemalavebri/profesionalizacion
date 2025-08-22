```c#
using System;
using OpenQA.Selenium;               // Interfaces para interactuar con navegador
using OpenQA.Selenium.Edge;          // Controlador para Microsoft Edge
using OpenQA.Selenium.Support.UI;    // Para esperas explícitas

class Program
{
    static void Main()
    {
        // Opciones para Edge (puedes configurar opciones aquí si quieres)
        EdgeOptions options = new EdgeOptions();

        // Por ejemplo, abrir Edge maximizado
        options.AddArgument("--start-maximized");

        // Instanciar el driver para Edge, controlará el navegador Edge
        using (IWebDriver driver = new EdgeDriver(options))
        {
            // Navegar a una página web (reemplaza con la URL que necesites)
            driver.Navigate().GoToUrl("https://example.com/login");

            // Crear espera explícita: espera hasta 10 segundos para condición
            WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(10));

            // Espera que exista el elemento con ID "username"
            wait.Until(ExpectedConditions.ElementExists(By.Id("username")));

            // Encontrar el campo usuario por ID y escribir texto
            IWebElement campoUsuario = driver.FindElement(By.Id("username"));
            campoUsuario.SendKeys("mi_usuario");

            // Encontrar el campo contraseña y escribir
            IWebElement campoPassword = driver.FindElement(By.Id("password"));
            campoPassword.SendKeys("mi_contraseña_segura");

            // Encontrar botón de login y hacer clic
            IWebElement botonLogin = driver.FindElement(By.Id("loginButton"));
            botonLogin.Click();

            // Esperar hasta que el mensaje de bienvenida sea visible
            wait.Until(ExpectedConditions.ElementIsVisible(By.Id("bienvenida")));

            // Obtener el texto del mensaje de bienvenida y mostrarlo
            IWebElement mensajeBienvenida = driver.FindElement(By.Id("bienvenida"));
            string texto = mensajeBienvenida.Text;
            Console.WriteLine("Texto encontrado: " + texto);

            // Otros ejemplos de búsqueda por clase, CSS y XPath
            var elementoClase = driver.FindElement(By.ClassName("nombre-clase"));
            var elementoCss = driver.FindElement(By.CssSelector("div.contenedor > p"));
            var elementoXPath = driver.FindElement(By.XPath("//div[@id='seccion']//a"));

            // Hacer clic en elemento localizado por XPath
            elementoXPath.Click();

            // Pausa para inspeccionar antes de cerrar
            Console.WriteLine("Presiona cualquier tecla para salir...");
            Console.ReadKey();
        }
        // Al salir del using, el navegador se cerrará automáticamente
    }
}



```