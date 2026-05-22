# Project Structure

## Business Umbrella

Buzzooka is the parent company. It should hold company-level strategy, brand, operations, sales systems, service delivery, and shared assets.

## Product Projects

Products like CLINICPILOTX should live in their own folders because they have their own roadmap, users, code, workflows, assets, sales materials, and technical architecture.

Recommended top-level split:

- `Buzzooka` - parent company, agency/service business, internal operations.
- `Buzzooka-Clients` - external client work, separated by client name.
- `Buzzooka-Products` - owned products such as CLINICPILOTX, FanFlow, Prime10X if applicable.
- `Buzzooka-Automations` - reusable automation templates, internal tools, shared n8n/Make workflows.

## CLINICPILOTX Role

CLINICPILOTX is an owned Buzzooka product, not a client project. Treat it like a product company inside Buzzooka:

- It needs its own product roadmap.
- It needs its own customer-facing sales assets.
- It needs a technical architecture that can scale beyond one client.
- It can reuse Buzzooka automation capabilities, but should not be mixed with random agency client work.

## Suggested Build Philosophy

Use Lovable as the rapid frontend/dashboard builder while it is useful. Use this folder to manage prompts, product specs, QA, and architecture. Move source code into a GitHub/local repo when the project needs deeper engineering control.
