# Andes Stump Grinding

A professional Jekyll-based landing page for Andes Stump Grinding.

## Website

Visit us at: [andeshomeservices.com](https://andeshomeservices.com)

## Jekyll Setup

This site is built with [Jekyll](https://jekyllrb.com/), a static site generator that works seamlessly with GitHub Pages.

### Prerequisites

- Ruby (2.7 or higher)
- RubyGems (included with Ruby)
- Bundler (installed via RubyGems)

### Installing Ruby and RubyGems on Windows 11

> **⚠️ IMPORTANT: Run PowerShell as Administrator**  
> Many installation steps require Administrator privileges. Right-click PowerShell and select "Run as Administrator" before proceeding.

#### Step 1: Download and Install Ruby

1. **Download RubyInstaller:**
   - Visit [RubyInstaller.org](https://rubyinstaller.org/)
   - Download the **Ruby+DevKit** installer (required for Jekyll)
     - Choose the latest version (e.g., Ruby 3.2.x with DevKit)
     - Download the 64-bit version for Windows 11

2. **Install Ruby:**
   - Right-click the installer and select "Run as Administrator"
   - **Important:** Check the box to "Add Ruby executables to your PATH"
   - Complete the installation

#### Step 2: Set Up MSYS2 Development Tools

> **⚠️ CRITICAL: Run PowerShell as Administrator**

After Ruby installation:

1. **Open PowerShell as Administrator:**
   - Right-click PowerShell
   - Select "Run as Administrator"

2. **Run the DevKit setup:**
   ```powershell
   ridk install
   ```

3. **Select option 3:**
   - You'll see a menu with options 1, 2, and 3
   - **Select option 3** to install MSYS2 and the full development toolchain
   - This is required for compiling native extensions like `bigdecimal`

4. **Wait for installation:**
   - MSYS2 download and installation takes 5-10 minutes
   - Keep the window open until completion

5. **Close and reopen PowerShell as Administrator:**
   - Close the current PowerShell window
   - Open a new PowerShell window **as Administrator**
   - This is required for changes to take effect

6. **Verify MSYS2 is working:**
   ```powershell
   ridk exec sh -c "echo 'MSYS2 is working'"
   ```
   - If you see "MSYS2 is working", the setup is correct

#### Step 3: Verify Ruby Installation

1. **Open PowerShell as Administrator**

2. **Check Ruby and RubyGems versions:**
   ```powershell
   ruby -v
   gem -v
   ```
   - You should see version numbers for both

#### Step 4: Install Bundler

```powershell
gem install bundler
```

#### Step 5: Install Jekyll Dependencies

1. **Navigate to your project directory:**
   ```powershell
   cd C:\Users\aege2\Documents\andes-home-services
   ```

2. **Install dependencies:**
   ```powershell
   bundle install
   ```

### Local Development

Once installation is complete:

1. **Build and serve the site:**
   ```powershell
   bundle exec jekyll serve
   ```

2. **View the site:**
   - Open your browser to `http://localhost:4000`
   - The site will automatically rebuild when you make changes

### Building for Production

```powershell
bundle exec jekyll build
```

The generated site will be in the `_site` directory.

## Troubleshooting

### Common Issues

**Ruby or gem commands not recognized:**
- Restart your computer after installation
- Or manually add Ruby to your PATH environment variable

**Local build issues:**
- Run `bundle update` to update dependencies
- Clear Jekyll cache: `bundle exec jekyll clean`

## GitHub Pages Setup

GitHub Pages automatically builds Jekyll sites. To deploy:

1. Push this repository to GitHub
2. Go to Settings > Pages in your GitHub repository
3. Select the branch (usually `main` or `master`) and folder (`/ (root)`)
4. GitHub Pages will automatically build and deploy your Jekyll site
5. Your site will be available at `https://[your-username].github.io/andes-home-services/`

**Note:** GitHub Pages uses Jekyll by default, so if you have a `_config.yml` file, it will automatically build your site.

## Custom Domain Setup

To use your custom domain `andeshomeservices.com`:

1. In your GitHub repository, go to Settings > Pages
2. Under "Custom domain", enter `andeshomeservices.com`
3. Configure DNS records with your domain provider:
   - Add a CNAME record pointing `andeshomeservices.com` to `[your-username].github.io`
   - Or add A records pointing to GitHub Pages IP addresses:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
4. GitHub will automatically create a `CNAME` file in your repository

## Project Structure

```
andes-home-services/
├── _config.yml          # Jekyll configuration
├── _layouts/            # HTML templates
│   └── default.html     # Default page layout
├── Gemfile              # Ruby dependencies
├── index.html           # Main landing page
├── styles.css           # Stylesheet
└── README.md            # This file
```

## Configuration

Site settings can be modified in `_config.yml`:
- Site title and description
- Contact information (email, phone)
- Plugins

## Images

The site uses free stock images from Unsplash related to stump grinding and tree services. These are loaded directly from their CDN. For production, you may want to:

1. **Keep using Unsplash** - Free, high-quality images (no attribution required for Unsplash Source API)
2. **Download and host locally** - Better performance and control
   - Create an `images/` folder
   - Download images from Unsplash
   - Update image paths in `index.html` to point to local files using `{{ '/images/filename.jpg' | relative_url }}`
3. **Use your own photos** - Replace with actual photos of your work/services

## Updating Content

### Edit Site Information

Update `_config.yml` to change:
- Site title
- Contact email and phone

### Edit Page Content

Edit `index.html` to modify the page content. The file uses:
- **Front matter** (YAML at the top) for page metadata
- **Jekyll variables** like `{{ site.title }}` and `{{ site.email }}` for dynamic content
- **Liquid templating** for dynamic date generation

### Edit Styling

Modify `styles.css` to change the design and layout.

## Jekyll Features Used

- **Layouts** - Reusable page templates
- **Site Variables** - Centralized configuration in `_config.yml`
- **Liquid Templating** - Dynamic content generation
- **Automatic Build** - GitHub Pages builds Jekyll automatically
